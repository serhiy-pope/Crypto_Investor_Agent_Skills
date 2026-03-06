---
name: protocol-stage-detector
description: >
  Protocol Stage Detector v1.0 — two-module skill: (1) Stage Detector classifies a crypto
  protocol's maturity stage (Bootstrap / Growth / Expansion / Maturity / Decline) from
  TVL growth, revenue trend, and developer activity; plots x/y coordinates and outputs
  move-up/move-down triggers; (2) FV Target computes a five-band fair-value estimate
  (bear → real_lo → mid → real_hi → bull) anchored to stage-specific P/TVL or P/Fees
  multiples, calculates overheat and discount factors, and recommends position sizing.
  Use when the user asks to determine a protocol's stage, compute fair value bands,
  check if a token is overvalued relative to TVL/fees, size a position by stage,
  or integrate with crypto valuation protocol. Triggers include:
  "protocol stage", "стадія протоколу", "TVL growth stage", "DeFi life cycle",
  "protocol maturity", "FV bands", "P/TVL fair value", "overheat factor crypto",
  "protocol stage detector", "determine protocol stage".
---

# Protocol Stage Detector v1.0

Two modules that always run together: **Stage Detector** → **FV Target**.
Results feed valuation (crypto_valuation.md) and thesis synthesis (09_final_report.md).

---

## MODULE 1 — Stage Detector

### Input

```json
{
  "ticker": "TOKEN",
  "protocol": "Protocol Name",
  "category": "DeFi/L1/L2/GameFi/RWA/Other",
  "asof": "ISO-UTC",
  "price_now": null,
  "series": {
    "tvl_usd": [m1, m2, m3, m4, m5, m6, "latest_month"],
    "protocol_revenue_usd": [...],
    "active_addresses_daily": [...],
    "github_commits_monthly": [...]
  },
  "tokenomics": {
    "circulating_supply": null,
    "total_supply": null,
    "net_issuance_rate_pct": null,
    "staking_rate_pct": null
  },
  "consensus_next6m": {
    "tvl_growth_pct": null,
    "revenue_growth_pct": null
  },
  "fv_band": {"bear": null, "real_lo": null, "mid": null, "real_hi": null, "bull": null}
}
```

### Algorithm (deterministic)

1. **TVL growth (smoothed):** tvl_cagr_6m = CAGR over last 6 months.
2. **Revenue trend:** linear regression on protocol_revenue_usd → `revenue_trend ∈ {up, flat, down}`.
3. **Activity trend:** active_addresses 3m change → `activity_trend ∈ {up, flat, down}`.
4. **Stage classifier:**
   - tvl_cagr_6m > 50% annualized → **Bootstrap** (new, growing fast)
   - 20–50% → **Growth**
   - 5–20% → **Expansion**
   - ≤ 5% AND revenue_trend ∈ {flat, up} → **Maturity**
   - tvl declining OR revenue declining → **Decline**
5. **Coordinates x/y (0..1):**
   - `stage_idx`: Bootstrap=0.10, Growth=0.30, Expansion=0.50, Maturity=0.70, Decline=0.90
   - `within_stage_offset` = clamp((tvl_cagr − lower) / (upper − lower), 0..1)
   - `x = stage_idx + 0.08 × within_stage_offset`
   - `y = 0.5 × norm(revenue_margin) + 0.5 × activity_score`
     - norm(revenue_margin) = clamp(revenue/tvl × 10, 0..1)
     - activity_score = {up:1, flat:0.5, down:0}
6. **Overheat:** `overheat_factor = price_now / fv_band.real_hi` (if fv_band available)
7. **Confidence 0–100:** based on data completeness and metric consistency.
8. **Comment:** 3–5 bullets — what's driving the stage, risks, "what would move to adjacent stage".

### Output (Module 1)

```json
{
  "protocol_stage_dot": {
    "ticker": "TOKEN",
    "asof": "ISO-UTC",
    "stage": "Bootstrap|Growth|Expansion|Maturity|Decline",
    "x": 0.00,
    "y": 0.00,
    "tvl_cagr_6m_pct": 0.0,
    "revenue_trend": "up|flat|down",
    "activity_trend": "up|flat|down",
    "overheat_factor": 0.0,
    "confidence_0_100": 0,
    "move_up_triggers": ["TVL growth re-accelerates >30%", "revenue/TVL improves"],
    "move_down_triggers": ["TVL declining 3m+", "developer activity collapse"],
    "comment": "One-line — why here"
  },
  "evidence_paths": ["/evidence/<ticker>_stage_<date>.json"],
  "audit": {"version": "ProtocolStage v1.0", "ttl_days": 90}
}
```

**Protocol rules:**
- If stage = Decline AND overheat_factor > 1.10 → ORANGE class maximum (no GREEN/YELLOW).
- If Bootstrap/Growth AND revenue growing → allow pilot position with tight stop.
- If stage = Maturity AND developer activity declining → flag "early Decline risk" in comment.

---

## MODULE 2 — FV Target (P/TVL Bands)

Uses stage from Module 1 to set P/TVL anchor and bands, then computes 5 FV estimates.

### Stage Parameters (defaults)

| Stage | p_tvl_mid | band_real | band_bull | band_bear |
|---|---|---|---|---|
| Bootstrap | 5.0 | 0.40 | 0.80 | 0.50 |
| Growth | 4.0 | 0.30 | 0.60 | 0.40 |
| Expansion | 3.0 | 0.25 | 0.50 | 0.35 |
| Maturity | 2.0 | 0.20 | 0.40 | 0.25 |
| Decline | 1.0 | 0.15 | 0.25 | 0.20 |

Override via `stage_cfg` input field if sector norms differ.

### FV Band Formulas

```
FV_bear    = TVL × p_tvl_mid × (1 − band_bear)
FV_real_lo = TVL × p_tvl_mid × (1 − band_real)
FV_mid     = TVL × p_tvl_mid
FV_real_hi = TVL × p_tvl_mid × (1 + band_real)
FV_bull    = TVL × p_tvl_mid × (1 + band_bull)

Divide by circulating supply to get per-token price.
```

Alternative (if protocol has clear revenue): use P/Fees multiple instead of P/TVL.

### Factors

```
overheat_factor = price_now ÷ FV_real_hi
discount_factor = price_now ÷ FV_real_lo
```

### Position Sizing (base rule)

```python
BASE_ALLOCATION = 0.02  # 2% AUM (lower than equities default due to higher crypto volatility)
stage_w = {"Bootstrap": 0.3, "Growth": 0.6, "Expansion": 1.0, "Maturity": 1.2, "Decline": 0.2}.get(stage, 0.3)
pos_size = BASE_ALLOCATION × stage_w / max(overheat_factor, 0.5)
if overheat_factor > 1.20:
    pos_size = max(pos_size × 0.5, 0.005)
# Additional caps: Heat limits, class caps applied at decision step
```

### Alerts

- overheat_factor > 1.20 → "Token overheated vs FV"
- discount_factor < 0.80 AND stage ∈ {Growth, Expansion} → "Value zone — consider accumulation"
- price_now outside FV_bull / FV_bear → immediate notification

### Output (Module 2)

```json
{
  "ticker": "TOKEN",
  "asof": "ISO-UTC",
  "stage": "...",
  "inputs": {"price_now": 0.0, "tvl": 0.0, "p_tvl_current": 0.0},
  "p_tvl_anchor": {"p_tvl_mid": 0.0, "band_real": 0.00, "band_bull": 0.00, "band_bear": 0.00},
  "fv_band": {"bear": 0.0, "real_lo": 0.0, "mid": 0.0, "real_hi": 0.0, "bull": 0.0},
  "factors": {"overheat": 0.00, "discount": 0.00},
  "position_sizing": {"base_allocation": 0.02, "stage_w": 1.00, "pos_size_reco": 0.00},
  "alerts": ["..."],
  "notes": "if TVL < $1M → data quality too low; use P/Fees instead",
  "evidence_path": "/evidence/<ticker>_fv_<date>.json",
  "audit": {"version": "ProtocolFV v1.0", "ttl_days": 90}
}
```

---

## Combined Output Format

Return **both JSON blocks** (Module 1 + Module 2) plus one summary sentence (≤ 160 chars).

## Important Notes

- Use only provided data; no guesses. If data insufficient → confidence ≤ 50, list missing.
- For protocols without revenue → use TVL only; note as `"revenue_based": false`.
- TTL: Protocol Stage 90 days; FV Target 90 days (shorter than equities due to faster crypto changes).
- Language: match user's (English or Ukrainian) in comment and alerts fields.
- Always cross-check P/TVL with industry peers (DeFiLlama sector averages).
