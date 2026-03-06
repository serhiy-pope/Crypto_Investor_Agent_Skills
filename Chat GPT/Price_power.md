---
name: price-power
description: >
  Price Power v1.2.1 — measures a company's sustainable pricing power: can it raise prices
  above industry inflation without meaningful volume/share loss while maintaining margins?
  Scores 0–5 (PricePowerFactor) based on ASP vs inflation, demand elasticity, market
  concentration, margin sustainability after price hikes, and moat sources. Score feeds
  protocol step 6 (Moat & Drivers) and step 8 (Thesis Synthesis) as a size modifier.
  Use when the user asks to evaluate pricing power, check if a company can raise prices,
  analyze ASP vs inflation, measure demand elasticity, assess moat from pricing, or asks
  about competitive position and margin durability. Triggers include: "price power",
  "цінова влада", "pricing power", "ASP vs inflation", "еластичність попиту",
  "demand elasticity", "чи може компанія піднімати ціни", "PricePowerFactor",
  "маржа після підвищення цін", "margin after price increase", "pricing moat".
---

# Price Power v1.2.1

Assess sustainable pricing power: ability to raise prices above industry inflation without
meaningful volume/share loss and with margin retention. Result feeds step 6 (Moat & Drivers)
and step 8 (Synthesis) of protocol v1.2.1.

## Input

```json
{
  "ticker": "TICKER",
  "company": "Company Name",
  "asof": "ISO-UTC",
  "sector": "GICS",
  "geo": ["US", "EU"],
  "period_years": 5,
  "peers": ["Peer1", "Peer2"],
  "inflation_index": "industry_CPI|PPI|other",
  "data_sources": ["10-K/Q", "press_releases", "Nielsen/IRI", "industry_reports"],
  "price_events": [
    {"date": "YYYY-MM-DD", "product": "<name>", "price_change_pct": 3.5, "note": "list price increase"},
    {"date": "YYYY-MM-DD", "product": "<name>", "price_change_pct": 5.0, "note": "surcharge; fuel indexation"}
  ]
}
```

## Data to Collect

1. **Competition:** HHI, Top-5 share, entry/regulatory barriers, substitutes/digital alternatives.
2. **Price & volume dynamics:** instances of ≥3% price increase, volume reaction, market share; ASP vs industry inflation.
3. **Margins & recovery:** gross/op margin trends vs peers; sustainability of margins after price hikes.
4. **Demand elasticity:** estimate ΔQ%/ΔP% from public data or regression; classify < 0.5 inelastic / 0.5–1 moderate / > 1 elastic.
5. **Moat sources:** brand/differentiation, IP/patents, network/platforms, switching costs, regulation, cost leadership.
6. **Loss-of-power risks:** tech substitutes, antitrust, ESG pressure, commoditization.

## Methodology (deterministic)

- **ASP vs inflation:** `asp_vs_inflation_pp = (ASP_yoy − Infl_yoy) × 100`
- **ASP decomposition:** price vs mix effect (if data available)
- **Volume/share response:** `volume_response_pct` and `share_trend_pp` after each price event
- **Elasticity:** delta-method (ΔQ/ΔP) or simple regression of volume on ASP (sign and |b|)
- **Margin sustainability:** = `expand|flat|compress` in 4 quarters after price hike
- **Pass-through check:** correlation with cost index (CPI/PPI), lag in months (if r² high and lag short → it's cost pass-through, not genuine pricing power)

## Scoring Scale (0–5)

| Score | Condition |
|---|---|
| 5 | ≥2 documented price waves ≥3% each; asp_vs_inflation_pp ≥ +2 p.p.; share stable/growing; margin does not compress; elasticity < 0.5; explicit moat sources |
| 4 | ≥1 price hike ≥3%; asp_vs_inflation_pp ≥ +1 p.p.; share not deteriorating; margin ≥ flat; elasticity 0.5–0.8; moat sources present |
| 3 | Neutral: asp ≈ inflation; share stable; margin flat/slightly negative; elasticity ~1; moat sources moderate |
| 2 | Weak: asp below inflation or share drops on hikes; margin compresses; elasticity 1–1.5 |
| 1 | Very weak: price hikes → notable share and margin loss; elasticity > 1.5 |
| 0 | Absent: prices follow cost (pass-through), no differentiation; hike attempts break volume/share |

## Protocol Integration (v1.2.1)

- **PricePowerFactor** = round(score), range 1–5 (3 = neutral), used in step 8.
- **Size modifiers:** score ≥ 4 → size_bias +10%; score ≤ 2 → size_bias −15% (if no liquidity stops).
- **Gate:** if ValueTrap = STOP or Liquidity/Dilution = STOP → do NOT use high score to inflate size.
- **Monitoring:** add 2–3 triggers (e.g., "ASP_growth < CPI_Industry 2q", "share_loss > 100 b.p. 2q", "antitrust action").

## Output (strict JSON)

```json
{
  "ticker": "TICKER",
  "asof": "ISO-UTC",
  "price_power": {
    "score": 0,
    "verdict": "Yes|Partial|No",
    "evidence": {
      "hhi": 0,
      "top5_share_pct": 0,
      "asp_vs_inflation_pp": 0.0,
      "volume_response_pct": 0.0,
      "share_trend_pp": 0.0,
      "elasticity": {"estimate": 0.0, "band": "inelastic|moderate|elastic", "method": "delta|regression"},
      "margin_sustainability": "expand|flat|compress",
      "peer_compare": {"gm_pp_diff": 0.0, "opm_pp_diff": 0.0},
      "moat_sources": ["brand", "switching_costs"],
      "risks": ["antitrust", "substitutes", "commoditization"]
    },
    "size_modifiers": {"bias_pct": 0, "notes": []}
  },
  "method": {
    "period_years": 5,
    "elasticity_window_quarters": 8,
    "inflation_index": "CPI/PPI",
    "cost_pass_through": {"index": "PPI_input", "r2": 0.0, "lag_months": 0}
  },
  "evidence_paths": ["/evidence/<ticker>_price_power_<date>.json"],
  "audit": {"version": "PricePower v1.2.1", "ttl_days": 180}
}
```

## Important Notes

- Return one JSON + one summary line (≤ 160 chars).
- If critical metrics missing (ASP, volume/share, industry inflation) → set `verdict: "REVIEW"` in summary; list missing.
- Save to /evidence/<ticker>_price_power_<date>.json; TTL 180 days.
- Language: match user's (English or Ukrainian) in moat_sources, risks, notes.
