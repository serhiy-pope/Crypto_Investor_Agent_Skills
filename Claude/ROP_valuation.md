---
name: rop-valuation
description: >
  ROP v1.2.1 — Realist / Optimist / Pessimist three-scenario stock valuation by EPS × P/E
  anchored to life-cycle stage and LC-FV rings. Computes Bear/Base/Bull price corridors,
  expected return, alpha-gate vs SPY, and decision hint (Buy/Hold/Sell/Review). Use when
  the user asks to value a stock in three scenarios, run ROP analysis, build a Bull/Base/Bear
  price model, check if a stock beats SPY on a 5-year horizon, or integrate valuation into
  protocol steps 7–9. Triggers include: "ROP", "оцінка ROP", "три сценарії", "three-scenario
  valuation", "Bull Base Bear ціна", "ціновий коридор", "alpha gate SPY", "оцінити акцію
  по сценаріям", "Realist Optimist Pessimist", "expected return vs SPY".
---

# ROP v1.2.1 — Realist / Optimist / Pessimist

Standardized three-scenario stock valuation (Bull/Base/Bear) via EPS × P/E anchored to
life-cycle stage and LC-FV rings. Output: price corridor, expected return, alpha-gate vs SPY.
Compatible with protocol steps 7–9.

## Input

```json
{
  "ticker": "TICKER",
  "asof": "ISO-UTC",
  "price_now": null,
  "shares_mn": null,
  "rev0_usd": null,
  "net_margin_now_pct": null,
  "cagr5y_pct": {"min": null, "med": null, "max": null},
  "target_margin5y_pct": {"bear": null, "base": null, "bull": null},
  "pe_hist_percentiles": {"p25": null, "p50": null, "p75": null},
  "horizon_years": 5,
  "stage": "EarlyGrowth|Expansion|Shakeout|Maturity|Decline|null",
  "lc_fv_cfg": null,
  "scenario_weights": [0.25, 0.5, 0.25],
  "spy_exp_return": 0.08,
  "alpha_hurdle_pp": 2,
  "share_change_plans": {"bear": 0.0, "base": 0.0, "bull": 0.0},
  "notes": ""
}
```

## Formulas

```
REVn     = REV0 × (1 + CAGR)^N
NInvn    = REVn × Margin
SHARESn  = SHARES × (1 + share_change)
EPSn     = NInvn ÷ SHARESn
Price_n  = EPSn × PE_n
```

## PE Selection (stage-aware)

Base: use historical `{p25, p50, p75}`.

Cross-check vs LC-FV `stage_anchor` (pe_mid and bands). Constrain:
- `PE_low ≥ pe_mid × (1 − band_pess)`
- `PE_high ≤ pe_mid × (1 + band_opt)`

If LC-FV absent → use historical percentiles without constraint.

**For losses** (EPSn < 0): compute price via EV/S and convert to equity (note in `notes`).

## Integrations

- `price_corridor = [Price_bear; Price_bull]` at horizon N
- `expected_price = Σ(Price_scen × weight_scen)`
- `expected_return_ticker = expected_price ÷ price_now − 1`
- `alpha_gate = PASS` if `(expected_return_ticker − spy_exp_return) ≥ alpha_hurdle_pp/100`

**Sanity:** do not change SHARES without buyback/dilution plans; if plans exist — apply per scenario.

## Output (strict JSON)

```json
{
  "ticker": "TICKER",
  "asof": "ISO-UTC",
  "inputs": {
    "price_now": 0.0, "rev0_usd": 0.0, "shares_mn": 0.0,
    "cagr5y_pct": {"min": 0.0, "med": 0.0, "max": 0.0},
    "target_margin5y_pct": {"bear": 0.0, "base": 0.0, "bull": 0.0},
    "pe_hist_percentiles": {"p25": 0.0, "p50": 0.0, "p75": 0.0},
    "horizon_years": 5, "stage": "Maturity"
  },
  "pe_anchor": {"pe_mid": 15, "band_real": 0.10, "band_opt": 0.20, "band_pess": 0.15},
  "scenarios": [
    {"name": "Pessimist", "cagr_pct": 0.0, "margin_pct": 0.0, "pe": 0.0, "shares_mn": 0.0, "eps": 0.0, "price": 0.0, "weight": 0.25},
    {"name": "Realist",   "cagr_pct": 0.0, "margin_pct": 0.0, "pe": 0.0, "shares_mn": 0.0, "eps": 0.0, "price": 0.0, "weight": 0.50},
    {"name": "Optimist",  "cagr_pct": 0.0, "margin_pct": 0.0, "pe": 0.0, "shares_mn": 0.0, "eps": 0.0, "price": 0.0, "weight": 0.25}
  ],
  "price_corridor": {"bear": 0.0, "base": 0.0, "bull": 0.0},
  "expected_price": 0.0,
  "expected_return_ticker": 0.0,
  "alpha_gate": "PASS|FAIL",
  "spy_exp_return": 0.08,
  "expected_excess_return_pp": 0.0,
  "decision_hint": "Buy|Hold|Sell|Review",
  "notes": "if EPS<0 → used EV/S; buyback/dilution applied per scenario",
  "audit": {"version": "ROP v1.2.1", "ttl_days": 180}
}
```

## One-liner (for step 8)

`«Base upside = +X%, bear downside = −Y%; alpha vs SPY = +Z п.п.; решение: Buy/Hold/Sell.»`

## Important Notes

- Minimize adjectives; numbers are primary. Tables: compact, no unnecessary zeros.
- If input data insufficient → return `decision_hint: "Review"` and list missing in notes.
- Save to /evidence/<ticker>_rop_<date>.json; TTL 180 days.
- Language: match user's (English or Ukrainian).
