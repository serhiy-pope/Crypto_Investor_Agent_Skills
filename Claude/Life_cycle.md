---
name: life-cycle
description: >
  Life-Cycle v1.2.1 — two-module skill: (1) Stage Detector classifies a company's
  life-cycle stage (EarlyGrowth / Expansion / Shakeout / Maturity / Decline) from
  revenue CAGR and margin trend, plots x/y coordinates, and outputs move-up/move-down
  triggers; (2) FV Target computes a five-ring fair-value hyperbola (pess → real_lo →
  mid → real_hi → opt) anchored to stage-specific P/E multiples, calculates overheat
  and discount factors, and recommends position sizing. Use when the user asks to
  determine a company's life-cycle stage, plot a life-cycle dot, compute fair value
  rings, check if a stock is overheated or in a value zone, size a position by stage,
  or integrate with ROP / β-Stress IRR (protocol steps 7–9). Triggers include:
  "життєвий цикл", "стадія компанії", "life cycle stage", "life-cycle detector",
  "FV target", "кільця справедливої вартості", "fair value rings", "overheat factor",
  "LC-FV", "stage detector", "determine company stage", "визнач стадію".
---

# Life-Cycle v1.2.1

Two modules that always run together: **Stage Detector** → **FV Target**.
Results feed protocol steps 7–9 (ROP, β-Stress IRR, Decision/Orders).

---

## MODULE 1 — Stage Detector

### Input

```json
{
  "ticker": "TICKER",
  "asof": "ISO-UTC",
  "price_now": null,
  "series": {
    "revenue_usd": [y1, y2, y3, y4, y5, "ltm_or_last_fy"],
    "gross_margin_pct": [...],
    "op_margin_pct": [...],
    "fcf_margin_pct": [...],
    "eps_annual": [...]
  },
  "segm_signals": {
    "services_rev_growth_yoy_pct": null,
    "hardware_units_trend": "up|flat|down|null"
  },
  "capital_return": {
    "buyback_shrinkage_3y_pct": null,
    "net_dilution_last12m_pct": null
  },
  "consensus_next2y": {
    "rev_cagr_pct": null,
    "eps_cagr_pct": null
  },
  "fv_ring": {"pess": null, "real_lo": null, "mid": null, "real_hi": null, "opt": null}
}
```

### Algorithm (deterministic)

1. **Smoothed growth:** rev_cagr_4y = CAGR last 4 years (winsorize outliers).
2. **Margin trend:** linear regression on op_margin_pct over 12–16 quarters → `margin_trend ∈ {up, flat, down}`.
3. **Stage classifier:**
   - rev_cagr > 30% → **EarlyGrowth**
   - 15–30% → **Expansion**
   - 5–15% → **Shakeout**
   - ≤ 5% AND margin_trend ∈ {flat, up} → **Maturity**
   - otherwise → **Decline**
4. **Coordinates x/y (0..1):**
   - `stage_idx`: Seed=0.10, Early=0.30, Expansion=0.50, Shakeout=0.65, Maturity=0.80, Decline=0.95
   - `within_stage_offset` = clamp((rev_cagr − lower) / (upper − lower), 0..1); Maturity bounds [0; 5]
   - `x = stage_idx + 0.08 × within_stage_offset`
   - `y = 0.5 × norm(op_margin_last) + 0.5 × trend_score`
     - norm(op_margin_last) = clamp(op_margin_last / 30, 0..1)
     - trend_score = {up:1, flat:0.5, down:0}
5. **Overheat:** `overheat_factor = price_now / fv_ring.real_hi` (if fv_ring available)
6. **Confidence 0–100:** based on data completeness and metric consistency.
7. **Comment:** 3–5 bullets — what's driving the stage, risks, "what would move to adjacent stage".

### Output (Module 1)

```json
{
  "life_cycle_dot": {
    "ticker": "TICKER",
    "asof": "ISO-UTC",
    "stage": "EarlyGrowth|Expansion|Shakeout|Maturity|Decline",
    "x": 0.00,
    "y": 0.00,
    "rev_cagr_4y_pct": 0.0,
    "margin_trend": "up|flat|down",
    "op_margin_last_pct": 0.0,
    "fcf_margin_last_pct": 0.0,
    "overheat_factor": 0.0,
    "confidence_0_100": 0,
    "basket_map": ["Steady-Compounder"],
    "move_up_triggers": ["rev_growth ≥ 10–12% 2q+", "operating leverage: OPM ↑"],
    "move_down_triggers": ["rev_growth ≤ 0% 4q", "GM compression"],
    "comment": "One-line — why here"
  },
  "evidence_paths": ["/evidence/<ticker>_life_cycle_<date>.json"],
  "audit": {"version": "LifeCycle v1.2.1", "ttl_days": 180}
}
```

**Protocol rules:**
- If stage ∈ {Maturity, Shakeout} AND overheat_factor > 1.30 → reduce max_size by 50% (Speculator position).
- If Early/Expansion AND consensus rev_cagr_next2y ≥ 20% → allow ExpansionCompounder (with PASS from Eureka/Liquidity).

---

## MODULE 2 — FV Target (Life-Cycle Hyperbola)

Uses stage from Module 1 to set P/E anchor and bands, then computes 5 FV rings.

### Stage Parameters (defaults)

| Stage | pe_mid | band_real | band_opt | band_pess |
|---|---|---|---|---|
| EarlyGrowth | 35 | 0.25 | 0.50 | 0.35 |
| Expansion | 28 | 0.20 | 0.35 | 0.30 |
| Shakeout | 20 | 0.15 | 0.25 | 0.25 |
| Maturity | 15 | 0.10 | 0.20 | 0.15 |
| Decline | 11 | 0.08 | 0.15 | 0.12 |

Override via `stage_cfg` input field if sector norms differ.

### FV Ring Formulas

```
FV_pess    = eps_fwd × pe_mid × (1 − band_pess)
FV_real_lo = eps_fwd × pe_mid × (1 − band_real)
FV_mid     = eps_fwd × pe_mid
FV_real_hi = eps_fwd × pe_mid × (1 + band_real)
FV_opt     = eps_fwd × pe_mid × (1 + band_opt)
```

### Factors

```
overheat_factor = price_now ÷ FV_real_hi
discount_factor = price_now ÷ FV_real_lo
```

### Position Sizing (base rule)

```python
BASE_ALLOCATION = 0.03  # 3% AUM
stage_w = {"EarlyGrowth": 0.5, "Expansion": 0.75, "Shakeout": 1.0, "Maturity": 1.2}.get(stage, 0.3)
pos_size = BASE_ALLOCATION × stage_w / max(overheat_factor, 0.5)
if overheat_factor > 1.30:
    pos_size = max(pos_size × 0.5, 0.01)
# Additional caps: ATR/VAR/role_caps applied at Decision step
```

### Alerts

- overheat_factor > 1.20 → "Мультиплікатор перегрітий"
- discount_factor < 0.85 AND stage ∈ {Expansion, Maturity} → "Зона value — розглянути докупку"
- price_now outside FV_opt / FV_pess → immediate notification

### Output (Module 2)

```json
{
  "ticker": "TICKER",
  "asof": "ISO-UTC",
  "stage": "...",
  "inputs": {"price_now": 0.0, "eps_fwd": 0.0, "pe_fwd": 0.0},
  "pe_anchor": {"pe_mid": 0.0, "band_real": 0.00, "band_opt": 0.00, "band_pess": 0.00},
  "fv_ring": {"pess": 0.0, "real_lo": 0.0, "mid": 0.0, "real_hi": 0.0, "opt": 0.0},
  "factors": {"overheat": 0.00, "discount": 0.00},
  "position_sizing": {"base_allocation": 0.03, "stage_w": 1.00, "pos_size_reco": 0.00},
  "alerts": ["..."],
  "notes": "if EPS < 0 → used EV/S; see detector",
  "evidence_path": "/evidence/<ticker>_lc_fv_<date>.json",
  "audit": {"version": "LC-FV v1.2.1", "ttl_days": 180}
}
```

---

## Combined Output Format

Return **both JSON blocks** (Module 1 + Module 2) plus one summary sentence (≤ 160 chars).

## Important Notes

- Use only provided series data; no guesses. If data insufficient → confidence ≤ 50, list missing in evidence file.
- For EPS < 0 (Seed/transition): use EV/S instead of P/E; set `"use_ev_s": true` in notes.
- x/y coordinates must be in 0..1 range and match the stage.
- TTL: Life-Cycle 180 days; FV Target 180 days.
- Language: match user's (English or Ukrainian) in comment and alerts fields.
