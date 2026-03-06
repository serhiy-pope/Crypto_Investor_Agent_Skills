---
name: eureka-test
description: >
  Eureka-тест v1.2.1 — Quality of Earnings & Accruals scorer. Evaluates 8 metrics
  (QoE = CFO/NI, FCF vs Earnings, Sloan Accrual Ratio, Beneish M-Score, DSO days,
  Inventory Days, SBC/CFO, Capex & Intangibles) and returns a weighted EurekaScore
  0–100 with status Gold/Silver/Bronze/Red Flag plus protocol hooks (size bias, IRR
  hurdle delta). Use when the user asks to check earnings quality, run Eureka test,
  evaluate accruals, assess QoE, check Sloan or Beneish score, review SBC burden,
  or assess whether reported earnings are cash-backed. Triggers include: "Eureka test",
  "еврика тест", "quality of earnings", "якість прибутку", "QoE", "accruals check",
  "Sloan ratio", "Beneish M-Score", "SBC to CFO", "earnings quality score",
  "перевір якість прибутку", "Red Flag Gold Silver Bronze". Run at protocol step 7
  before ROP and Life-Cycle FV Target; repeat on quarterly reports and major M&A.
---

# Eureka-test v1.2.1 — Quality of Earnings & Accruals

Scores earnings quality via 8 weighted metrics. Output feeds Basket Mapper, ROP,
and β-Stress IRR. Run at step 7 "Deep Valuation" before ROP / LC-FV Target.

**When to run:** Step 7, quarterly reports, significant M&A, audit changes.

## Input

```json
{
  "ticker": "TICKER",
  "asof": "ISO-UTC",
  "periods": ["FY2023", "FY2024", "LTM"],
  "mktcap": null,
  "price_now": null,
  "statements": {
    "income":   {"FY2023": {}, "FY2024": {}, "LTM": {}},
    "balance":  {"FY2023": {}, "FY2024": {}, "LTM": {}},
    "cashflow": {"FY2023": {}, "FY2024": {}, "LTM": {}}
  },
  "params": {
    "weights": {
      "qoe": 1.0, "fcf_vs_earnings": 0.8, "sloan": 1.0, "beneish": 1.0,
      "dso": 0.7, "inventory_days": 0.7, "sbc_to_cfo": 0.8, "capex_intangibles": 0.6
    },
    "sector_overrides": {"financials": false, "reits": false}
  }
}
```

## 8 Metrics & Thresholds

| Metric | Formula | Red Flag Threshold |
|---|---|---|
| QoE | CFO ÷ NI | < 0.80 |
| FCF vs Earnings | FCF/MktCap vs NI/MktCap | FCF yield noticeably < earnings yield |
| Sloan Accrual Ratio | \|ΔCA − ΔCash − ΔCL + ΔSTD\| ÷ Avg Assets | > 8% |
| Beneish M-Score | 8-variable manipulation model | > −1.78 |
| DSO | AR ÷ Revenue × 365 | YoY growth > 15 days |
| Inventory Days | Inv ÷ COGS × 365 | YoY growth > 15 days |
| SBC ÷ CFO | SBC / Operating Cash Flow | > 20% |
| Capex & Intangibles | Capex to sales + Δ intangibles | Suspiciously low Capex with rising intangibles |

Each metric: score 0–15 (0 = worst, 15 = well above threshold).

## Scoring

```
total_raw = Σ(score_i × weight_i)
max_raw   = 15 × Σ(weight_i)
EurekaScore = round(100 × total_raw ÷ max_raw)
```

**Status tiers:**

| Score | Status | Protocol action |
|---|---|---|
| 80–100 | 🥇 Gold | size_bias = +10%; min_IRR_hurdle −1 p.p. |
| 60–79 | 🥈 Silver | size_bias = 0…+5%; no IRR shift |
| 40–59 | 🥉 Bronze | size_bias = −15%; min_IRR_hurdle +2 p.p. |
| < 40 | 🚩 Red Flag | protocol_action = STOP (unless obvious one-off anomaly → PAUSE) |

## Sector Overrides

- **Banks/Financials:** ignore Inventory Days; use P/TBV and credit provisions as context.
- **REITs:** QoE and Cash conversion are critical; treat Capex as sustaining vs growth; use AFFO.
- **Software:** SBC threshold raised to 25%; soften if FCF is clearly growing.

## Output (strict JSON)

```json
{
  "ticker": "TICKER",
  "asof": "ISO-UTC",
  "periods": ["FY2023", "FY2024", "LTM"],
  "metrics": {
    "qoe":             {"FY2023": 0.95, "FY2024": 0.88, "LTM": 0.72, "flag": true, "threshold": 0.80, "score": 6},
    "fcf_vs_earnings": {"FY2023": "ok", "FY2024": "ok", "LTM": "worse", "score": 8},
    "sloan":           {"FY2023": 0.02, "FY2024": 0.05, "LTM": 0.10, "flag": true, "threshold": 0.08, "score": 4},
    "beneish_m":       {"FY2023": -2.3, "FY2024": -2.0, "LTM": -1.6, "flag": true, "threshold": -1.78, "score": 3},
    "dso_days":        {"FY2023": 42, "FY2024": 46, "LTM": 55, "yoy_flag": true, "score": 7},
    "inventory_days":  {"FY2023": 28, "FY2024": 33, "LTM": 39, "yoy_flag": true, "score": 7},
    "sbc_to_cfo_pct":  {"FY2023": 12, "FY2024": 18, "LTM": 27, "flag": true, "threshold": 20, "score": 5},
    "capex_intangibles": {"capex_to_sales": {"FY2023": 5.1, "FY2024": 4.7, "LTM": 3.2}, "delta_intangibles_pct_sales": 2.1, "flag": true, "score": 6}
  },
  "weights": {"qoe": 1.0, "fcf_vs_earnings": 0.8, "sloan": 1.0, "beneish": 1.0, "dso": 0.7, "inventory_days": 0.7, "sbc_to_cfo": 0.8, "capex_intangibles": 0.6},
  "eureka_score": 57,
  "status": "Bronze",
  "protocol_hooks": {
    "size_bias_pct": -15,
    "irr_hurdle_pp_delta": 2,
    "recommendation": "Review before buy; seek QoE>0.9 and SBC<15"
  },
  "narrative": "Earnings quality deteriorating third year; accruals rising; Beneish approaching threshold; SBC high.",
  "risks": ["receivables bloat", "cash squeeze", "aggressive intangibles capitalization"],
  "improvement_catalysts": ["working capital cleanup", "SBC reduction", "FCF conversion improvement"],
  "evidence_paths": ["/evidence/<ticker>_eureka_<date>.json"],
  "audit": {"version": "Eureka v1.2.1", "ttl_days": 180}
}
```

## Optional Markdown Table

```
### Eureka-тtest: {Ticker}, {Period}
| Metric | 2023 | 2024 | LTM | Threshold | Comment |
```

## Important Notes

- Use only provided statements data; no guesses.
- Always return `eureka_json` plus one summary line (≤ 160 chars).
- Apply `sector_overrides`; if critical fields missing (CFO, NI, AR, Inv) → status = "Review", list missing.
- Save to /evidence/<ticker>_eureka_<date>.json; TTL 180 days.
- Language: match user's (English or Ukrainian).
