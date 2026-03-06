---
name: tokenomics-health
description: >
  Tokenomics Health v1.0 — Quality of Token Economics scorer. Evaluates 8 metrics
  (emission rate, supply inflation, unlock schedule, VC concentration, fee capture ratio,
  staking rate, treasury sustainability, token utility) and returns a weighted
  TokenomicsScore 0–100 with status Gold/Silver/Bronze/Red Flag plus protocol hooks
  (size bias, class cap). Use when the user asks to check tokenomics quality,
  run tokenomics health check, evaluate inflation risk, assess unlock schedule,
  check VC cliff risk, analyze fee capture vs emissions, review treasury sustainability,
  or assess whether a token has real utility backing. Triggers include: "tokenomics",
  "токеноміка", "tokenomics check", "emission rate", "unlock schedule", "VC cliff",
  "fee capture", "staking rate", "treasury", "token health", "перевір токеноміку",
  "Red Flag Gold Silver Bronze crypto".
---

# Tokenomics Health v1.0 — Quality of Token Economics

Scores tokenomics quality via 8 weighted metrics. Output feeds class cap decisions,
position sizing modifiers, and 06_asset_card Block 3 (Tokenomics).

**When to run:** Before GREEN/YELLOW entry; on major tokenomics changes; quarterly review.

## Input

```json
{
  "ticker": "TOKEN",
  "protocol": "Protocol Name",
  "asof": "ISO-UTC",
  "current_price": null,
  "market_cap": null,
  "fdv": null,
  "tokenomics": {
    "circulating_supply": null,
    "total_supply": null,
    "max_supply": null,
    "emission_rate_pct_annual": null,
    "burn_mechanism": false,
    "burn_rate_pct_annual": null
  },
  "distribution": {
    "team_pct": null,
    "investors_vc_pct": null,
    "community_ecosystem_pct": null,
    "treasury_pct": null,
    "public_sale_pct": null
  },
  "unlock_schedule": [
    {"date": "YYYY-MM-DD", "amount_pct_circulating": null, "recipient": "team|vc|ecosystem"},
    {"date": "YYYY-MM-DD", "amount_pct_circulating": null, "recipient": "..."}
  ],
  "protocol_economics": {
    "fee_revenue_annualized_usd": null,
    "token_emissions_annualized_usd": null,
    "staking_rate_pct": null,
    "treasury_usd": null,
    "treasury_runway_months": null
  },
  "params": {
    "weights": {
      "emission_rate": 1.0,
      "inflation_risk": 1.0,
      "unlock_risk": 1.0,
      "vc_concentration": 0.8,
      "fee_capture": 1.0,
      "staking_rate": 0.7,
      "treasury_health": 0.8,
      "token_utility": 1.0
    }
  }
}
```

## 8 Metrics & Thresholds

| Metric | Formula | Red Flag Threshold |
|---|---|---|
| Emission Rate | Net annual inflation of circulating supply | > 10% |
| Inflation Risk | Net issuance (gross emission − burn) / circulating supply | > 5% net |
| Unlock Risk | Largest single unlock event in next 90 days / circulating supply | > 10% in 90d |
| VC Concentration | Team + VC / total supply | > 35% combined |
| Fee Capture | Protocol fees annualized / token emissions annualized | < 0.3 |
| Staking Rate | % supply staked (aligned, locked) | < 10% |
| Treasury Health | Treasury runway in months at current burn | < 12 months |
| Token Utility | Real use cases: gas/governance/fee discount/collateral (0=none, 5=essential) | score < 2 |

Each metric: score 0–15 (0 = worst, 15 = well above threshold).

## Scoring

```
total_raw = Σ(score_i × weight_i)
max_raw   = 15 × Σ(weight_i)
TokenomicsScore = round(100 × total_raw ÷ max_raw)
```

**Status tiers:**

| Score | Status | Protocol action |
|---|---|---|
| 80–100 | 🥇 Gold | size_bias = +10%; GREEN class allowed |
| 60–79 | 🥈 Silver | size_bias = 0…+5%; GREEN/YELLOW allowed |
| 40–59 | 🥉 Bronze | size_bias = −15%; YELLOW max; monitor closely |
| < 40 | 🚩 Red Flag | class_cap = ORANGE max; position size capped at 0.5% |

## Category Overrides

- **BTC/ETH (base layer):** Skip VC concentration and emission rate as configured; use network issuance analysis instead.
- **L2s:** Treasury health is critical; treat sequencer fees as "fee revenue".
- **Governance tokens (pure):** Token utility score starts at 2 (governance = baseline utility).

## Output (strict JSON)

```json
{
  "ticker": "TOKEN",
  "asof": "ISO-UTC",
  "metrics": {
    "emission_rate":    {"value_pct": 0.0, "flag": false, "threshold": 10, "score": 0},
    "inflation_risk":   {"value_pct": 0.0, "flag": false, "threshold": 5, "score": 0},
    "unlock_risk":      {"next_90d_pct": 0.0, "date": "", "flag": false, "threshold": 10, "score": 0},
    "vc_concentration": {"team_vc_pct": 0.0, "flag": false, "threshold": 35, "score": 0},
    "fee_capture":      {"ratio": 0.0, "flag": false, "threshold": 0.3, "score": 0},
    "staking_rate":     {"value_pct": 0.0, "flag": false, "threshold": 10, "score": 0},
    "treasury_health":  {"runway_months": 0, "flag": false, "threshold": 12, "score": 0},
    "token_utility":    {"score_0_5": 0, "use_cases": [], "flag": false, "threshold": 2, "score": 0}
  },
  "weights": {
    "emission_rate": 1.0, "inflation_risk": 1.0, "unlock_risk": 1.0, "vc_concentration": 0.8,
    "fee_capture": 1.0, "staking_rate": 0.7, "treasury_health": 0.8, "token_utility": 1.0
  },
  "tokenomics_score": 0,
  "status": "Gold|Silver|Bronze|Red Flag",
  "protocol_hooks": {
    "size_bias_pct": 0,
    "class_cap": "GREEN|YELLOW|ORANGE",
    "recommendation": ""
  },
  "narrative": "One-line tokenomics summary",
  "risks": ["high inflation", "VC cliff in 60d", "no utility beyond governance"],
  "improvement_catalysts": ["fee switch activation", "buyback/burn program", "utility expansion"],
  "key_unlocks_next_6m": [
    {"date": "", "amount_pct": 0, "recipient": "", "risk_level": "high|medium|low"}
  ],
  "evidence_paths": ["/evidence/<ticker>_tokenomics_<date>.json"],
  "audit": {"version": "TokenomicsHealth v1.0", "ttl_days": 90}
}
```

## Optional Markdown Summary

```
### Tokenomics Health: {Token}, {Date}
| Metric | Value | Threshold | Status |
|---|---|---|---|
| Emission Rate | X% | ≤10% | ✓/✗ |
...
Overall: {score}/100 — {Gold/Silver/Bronze/Red Flag}
```

## Important Notes

- Use only provided data; no guesses.
- Always return `tokenomics_json` plus one summary line (≤ 160 chars).
- If critical fields missing (emission rate, unlock schedule, fee data) → status = "Review", list missing.
- Save to /evidence/<ticker>_tokenomics_<date>.json; TTL 90 days.
- Language: match user's (English or Ukrainian).
- Red Flag status = automatic ORANGE cap regardless of other factors. Inform user clearly.
