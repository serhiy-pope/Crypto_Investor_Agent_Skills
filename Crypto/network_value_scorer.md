---
name: network-value-scorer
description: >
  Network Value Scorer v1.0 — measures a crypto protocol's sustainable network effect strength:
  can it retain users and grow TVL/revenue without unsustainable token incentives?
  Scores 0–5 (NetworkValueFactor) based on organic user retention, TVL stickiness,
  fee revenue vs token emissions, developer ecosystem depth, and composability/moat.
  Score feeds protocol analysis step (06_asset_card, Block 5) and thesis synthesis
  (09_final_report) as a position sizing modifier. Use when the user asks to evaluate
  a protocol's network effects, check if TVL is organic or incentivized, analyze fee
  capture vs token dilution, assess developer ecosystem stickiness, or measure moat
  from composability. Triggers include: "network effect", "мережевий ефект",
  "TVL organic", "fee capture", "protocol moat", "NetworkValueFactor",
  "composability score", "developer retention", "чи органічний TVL".
---

# Network Value Scorer v1.0

Assess sustainable network value: ability to retain users and grow organically without
relying primarily on token incentives. Result feeds 06_asset_card (Block 5)
and 09_final_report (Block 2 Q rating).

## Input

```json
{
  "ticker": "TOKEN",
  "protocol": "Protocol Name",
  "category": "DeFi-DEX|DeFi-Lending|L1|L2|NFT|Other",
  "asof": "ISO-UTC",
  "period_months": 6,
  "peers": ["Peer1", "Peer2"],
  "data_sources": ["DeFiLlama", "Dune Analytics", "GitHub", "protocol docs"],
  "incentive_events": [
    {"date": "YYYY-MM-DD", "type": "liquidity_mining|airdrop|farm", "size_usd": 0, "note": ""},
    {"date": "YYYY-MM-DD", "type": "organic_growth", "note": "TVL growth without incentives"}
  ]
}
```

## Data to Collect

1. **TVL stickiness:** TVL retention after incentive programs end (% of peak retained after 30/90 days).
2. **Fee revenue:** protocol fees / token emissions ratio — high ratio = organic value capture.
3. **User retention:** DAU/MAU ratio trend; returning users vs new users.
4. **Developer ecosystem:** GitHub contributors, forks, integrations built on top.
5. **Composability:** number of protocols that integrate this one (money lego factor).
6. **Token emission dependency:** what % of TVL would disappear if token farming APY dropped to 0%.

## Methodology (deterministic)

- **Organic TVL ratio:** `organic_tvl_pct = (TVL retained after incentives end) / (peak TVL during incentives) × 100`
- **Fee capture ratio:** `fee_capture = protocol_fees_annualized / token_emissions_annualized`; > 1 = self-sustaining
- **Retention trend:** DAU 30d change, user cohort retention
- **Developer depth:** unique contributors (GitHub), external integrations count
- **Pass-through check:** if TVL is 90%+ from one whale or one farm — it's not organic network effect

## Scoring Scale (0–5)

| Score | Condition |
|---|---|
| 5 | Organic TVL ratio >80%; fee_capture >1.0; high DAU retention; 50+ external integrations; leading developer ecosystem |
| 4 | Organic TVL ratio 60–80%; fee_capture 0.5–1.0; stable DAU; 20+ integrations; active developer community |
| 3 | Neutral: TVL mixed organic/incentivized; fee_capture 0.2–0.5; moderate retention; some integrations |
| 2 | Weak: TVL drops >50% after incentives end; fee_capture < 0.2; poor retention; few integrations |
| 1 | Very weak: entirely incentive-dependent; no organic revenue; no developer activity outside core team |
| 0 | Absent: TVL = 100% farm; protocol would have near-zero TVL without token emissions |

## Protocol Integration

- **NetworkValueFactor** = round(score), range 0–5 (3 = neutral), used in 06_asset_card Block 5.
- **Size modifiers:** score ≥ 4 → size_bias +10%; score ≤ 2 → size_bias −20%.
- **Gate:** if score ≤ 1 → cap at ORANGE class maximum, never GREEN/YELLOW core.
- **Monitoring triggers:** add 2–3 triggers (e.g., "Fee capture ratio < 0.3 for 2 months", "TVL drops >30% post-incentive", "GitHub contributors drops >40%").

## Output (strict JSON)

```json
{
  "ticker": "TOKEN",
  "asof": "ISO-UTC",
  "network_value": {
    "score": 0,
    "verdict": "Strong|Moderate|Weak|Incentive-Only",
    "evidence": {
      "organic_tvl_ratio_pct": 0.0,
      "fee_capture_ratio": 0.0,
      "dau_trend": "up|flat|down",
      "external_integrations_count": 0,
      "github_contributors": 0,
      "token_emission_dependency_pct": 0.0,
      "composability_score": "high|medium|low",
      "moat_sources": ["network_effects", "composability", "developer_ecosystem"],
      "risks": ["incentive_dependency", "whale_concentration", "fork_risk"]
    },
    "size_modifiers": {"bias_pct": 0, "notes": []}
  },
  "method": {
    "period_months": 6,
    "incentive_events_analyzed": 0,
    "data_sources": ["DeFiLlama", "GitHub"]
  },
  "evidence_paths": ["/evidence/<ticker>_network_value_<date>.json"],
  "audit": {"version": "NetworkValue v1.0", "ttl_days": 90}
}
```

## Important Notes

- Return one JSON + one summary line (≤ 160 chars).
- If critical metrics missing (TVL history, fee data, GitHub) → set `verdict: "REVIEW"` in summary; list missing.
- Save to /evidence/<ticker>_network_value_<date>.json; TTL 90 days.
- Language: match user's (English or Ukrainian) in moat_sources, risks, notes.
- Key distinction: "TVL = total value locked" measures deposits; "protocol revenue/fees" measures real economic activity. Both needed for honest score.
