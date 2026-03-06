---
name: crypto-valuation
description: >
  Crypto Valuation v1.0 — three-scenario crypto asset valuation using on-chain multiples
  (P/TVL, P/Fees, NVT) anchored to protocol stage and cycle position. Computes Bear/Base/Bull
  price corridors, expected value, and alpha-gate vs BTC benchmark. Use when the user asks
  to value a crypto asset in three scenarios, run Bear/Base/Bull price model, check if a
  token beats BTC benchmark on horizon, or integrate valuation into decision protocol.
  Triggers include: "crypto valuation", "оцінка токену", "three scenarios crypto",
  "Bull Base Bear price", "P/TVL valuation", "NVT ratio model", "expected value crypto",
  "оцінити токен по сценаріям", "crypto fair value", "alpha gate BTC".
---

# Crypto Valuation v1.0 — Bear / Base / Bull Three-Scenario Model

Standardized three-scenario crypto asset valuation via on-chain multiples (P/TVL, P/Fees, NVT)
anchored to protocol stage and BTC cycle position. Output: price corridor, expected value, alpha-gate vs BTC.
Compatible with 06_asset_card, 08_scenario_map, and 09_final_report.

## Input

```json
{
  "ticker": "TOKEN",
  "protocol": "Protocol Name",
  "category": "L1|L2|DeFi|Other",
  "asof": "ISO-UTC",
  "price_now": null,
  "circulating_supply": null,
  "primary_multiple": "P/TVL|P/Fees|NVT|P/Revenue",
  "current_tvl_usd": null,
  "current_fees_annualized_usd": null,
  "current_transaction_volume_30d_usd": null,
  "stage": "Bootstrap|Growth|Expansion|Maturity|Decline|null",
  "p_multiple_hist_percentiles": {"p25": null, "p50": null, "p75": null},
  "horizon_months": 12,
  "scenario_weights": [0.20, 0.50, 0.30],
  "btc_exp_return_12m": 0.40,
  "alpha_hurdle_pp": 10,
  "notes": ""
}
```

## Valuation Multiples Guide

| Multiple | Formula | Best for |
|---|---|---|
| P/TVL | Market Cap / Total Value Locked | DeFi lending, DEXs |
| P/Fees | Market Cap / Annualized Protocol Fees | Fee-generating protocols |
| NVT | Market Cap / 30d Transaction Volume × 30 | L1s, payment chains |
| P/Revenue | Market Cap / Protocol Revenue (fees − emissions) | Mature protocols |

Choose the multiple most meaningful for the specific protocol. Note in output.

## Formulas

```
FV_scen = Projected_TVL(or Fees/Volume) × P_multiple_scen / Circulating_Supply
Expected_Price = Σ(FV_i × weight_i)
Expected_Return = Expected_Price / price_now − 1
Alpha = Expected_Return − btc_exp_return_12m
```

## Multiple Selection (stage-aware)

Base: use historical `{p25, p50, p75}` from CoinGecko / DeFiLlama history.

Cross-check vs protocol stage defaults:

| Stage | P/TVL mid | P/Fees mid |
|---|---|---|
| Bootstrap | 5–8x | 50–100x |
| Growth | 3–6x | 30–60x |
| Expansion | 2–4x | 20–40x |
| Maturity | 1–3x | 10–25x |
| Decline | 0.5–1.5x | 5–15x |

Constrain scenarios:
- Bear: P_multiple ≤ p25 × 0.8
- Base: P_multiple ≈ p50
- Bull: P_multiple ≤ p75 × 1.2

**Cycle adjustment:**
- Late bull / Euphoria: compress Bull multiple by 20% (risk of contraction)
- Bear market: compress Base multiple by 30%, expand Bear scenario weight to 40%

## Output (strict JSON)

```json
{
  "ticker": "TOKEN",
  "asof": "ISO-UTC",
  "primary_multiple": "P/TVL",
  "inputs": {
    "price_now": 0.0,
    "tvl_current": 0.0,
    "p_tvl_current": 0.0,
    "hist_percentiles": {"p25": 0.0, "p50": 0.0, "p75": 0.0},
    "horizon_months": 12,
    "stage": "Growth"
  },
  "scenarios": [
    {
      "name": "Bear",
      "tvl_12m_usd": 0.0,
      "p_multiple": 0.0,
      "market_cap": 0.0,
      "price": 0.0,
      "weight": 0.20,
      "key_assumption": ""
    },
    {
      "name": "Base",
      "tvl_12m_usd": 0.0,
      "p_multiple": 0.0,
      "market_cap": 0.0,
      "price": 0.0,
      "weight": 0.50,
      "key_assumption": ""
    },
    {
      "name": "Bull",
      "tvl_12m_usd": 0.0,
      "p_multiple": 0.0,
      "market_cap": 0.0,
      "price": 0.0,
      "weight": 0.30,
      "key_assumption": ""
    }
  ],
  "price_corridor": {"bear": 0.0, "base": 0.0, "bull": 0.0},
  "expected_price": 0.0,
  "expected_return_12m": 0.0,
  "alpha_vs_btc": 0.0,
  "alpha_gate": "PASS|FAIL",
  "btc_exp_return_12m": 0.40,
  "upside_downside_ratio": 0.0,
  "decision_hint": "Buy|Hold|Sell|Review",
  "notes": "if TVL-based; cycle position adjustment applied",
  "audit": {"version": "CryptoValuation v1.0", "ttl_days": 90}
}
```

## One-liner (for 09_final_report)

`«Base upside = +X%, bear downside = −Y%; alpha vs BTC = +Z pp; U/D = Z:1; decision: Buy/Hold/Sell.»`

## Important Notes

- Crypto multiples are far more volatile than equity multiples — wide bands are expected.
- Alpha hurdle vs BTC should be ≥10 pp (crypto-adjusted) vs SPY's typical 2 pp in equities.
- If current P/TVL > stage p75 → flag as "Potentially overvalued" in notes; reduce Bull weight.
- Minimize adjectives; numbers are primary.
- If input data insufficient → return `decision_hint: "Review"` and list missing in notes.
- Save to /evidence/<ticker>_crypto_val_<date>.json; TTL 90 days.
- Language: match user's (English or Ukrainian).
