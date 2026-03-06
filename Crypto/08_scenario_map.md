# Scenario Map — Crypto
### Modules 1–3 · Bear / Base / Bull · Action branches · Alerts

---

> **How to use**
> Filled when opening a position — before entry, not after.
> Three scenarios describe possible paths for the thesis to develop, not price forecasts.
> Probabilities must sum to 100% — this disciplines thinking.
> Update after major protocol events, on-chain metric changes, or BTC cycle shift.
> Main value: when the market falls, you know in advance — is it Base or Bear?

---

## HEADER

```
Token: ___
Date: ____-__-__
Price now: $___
BTC price now: $___
Horizon: ___ months
Class: GREEN / YELLOW / ORANGE
Current scenario: Bull / Base / Bear  (mark each week)
```

---

## BLOCK 1 — THREE SCENARIOS

### Template

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
🟢 BULL — [name]
Probability: ___%

What happens to the network/protocol: ___
Key assumptions: 1) ___  2) ___  3) ___
On-chain metrics in 12 months: TVL $___  Active addresses ___  Fees/Revenue ___
Valuation: ___x P/TVL (or NVT/P/Fees) → Price: $___  Potential: +___%

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
🟡 BASE — [name]
Probability: ___%
[analogously]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
🔴 BEAR — [name]
Probability: ___%
[analogously]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

EV = Σ (P_i × Price_i) = $___ (___% to current)
```

### Example: ETH

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
🟢 BULL — "Institutional wave + L2 flywheel"
Probability: 30%

ETH ETF inflows accelerate beyond $500M/week. L2 activity drives
base fee burn >1M ETH/year. Institutional tokenized assets on Ethereum
reach >$50B. DeFi TVL recovers to $80B+.

Assumptions:
1) BTC reaches new ATH >$150k, pulling ETH into alt season
2) ETH ETF weekly flows >$500M sustained for 2+ months
3) No major regulatory setback

TVL: $85B | Active addresses: 600k daily | Burn rate: >1M ETH/yr
Valuation: P/TVL ~12x → Price: $7,000 → Potential: +119%

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
🟡 BASE — "Steady growth, mid-cycle"
Probability: 50%

ETH tracks BTC with moderate outperformance. ETF flows positive
but not explosive. DeFi TVL stable at $50–65B. L2 growth continues.
No major regulatory changes.

Assumptions:
1) BTC consolidates $80–120k range
2) ETF flows positive $50–200M/week
3) No major protocol exploit or regulatory action

TVL: $55B | Active addresses: 480k daily | Burn rate: ~500k ETH/yr
Valuation: P/TVL ~7x → Price: $4,000 → Potential: +25%

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
🔴 BEAR — "BTC cycle breaks, regulatory pressure"
Probability: 20%

BTC drops below $60k, entering extended bear market.
ETH DeFi TVL collapses to <$25B. ETF outflows.
Regulatory action classifies ETH as security in US.

Assumptions:
1) BTC breaks below 200 DMA and stays there 90+ days
2) SEC enforces ETH security classification
3) Global macro deterioration (recession, DXY spike)

TVL: $22B | Active addresses: 280k daily | Burn rate: near zero (inflationary)
Valuation: P/TVL ~4x → Price: $1,800 → Potential: −44%
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

EV = $7,000×30% + $4,000×50% + $1,800×20% = $2,100 + $2,000 + $360 = $4,460 (+39%)
```

---

## BLOCK 2 — TRANSITION TRIGGERS

### Template
```
BASE → BULL: ✓ ___  ✓ ___
BASE → BEAR: ✗ ___  ✗ ___
BEAR → INVALIDATION: ✗ ___ → immediate review
```

### Example: ETH
```
BASE → BULL:
  ✓ ETH ETF weekly net inflows >$500M for 2 consecutive weeks
  ✓ DeFi TVL grows above $75B
  ✓ ETH/BTC ratio breaks above 0.065 and sustains

BASE → BEAR:
  ✗ BTC closes weekly below $60,000
  ✗ DeFi TVL falls below $35B
  ✗ ETH ETF outflows >$200M/week for 2 consecutive weeks
  ✗ SEC enforcement action against ETH as security

BEAR → INVALIDATION:
  ✗ DeFi TVL < $20B for two consecutive months → DeFi moat thesis broken
  ✗ Net ETH issuance turns > +2% annually for 3+ months → tokenomics broken
  ✗ Developer activity (GitHub commits) drops >50% in 6 months
  → Any of these: stop adding, review thesis
```

---

## BLOCK 3 — ACTIONS BY SCENARIO

### Template
```
On BULL: size to ___%, action: ___
On BASE: size ___%, action: ___
On BEAR: reduce to ___%, hedge: ___
```

### Example: ETH
```
On BULL:
  To 14% (max GREEN). Add on first Bull trigger confirmation.
  If drift >20% — trim in steps of 2%/month.

On BASE (current):
  6% (pilot). Hold, don't add until Bull triggers.
  If drift >18% — trim to 14%.

On BEAR:
  Reduce to 3% on first two Bear signals (BTC weekly below $60k + TVL <$35B).
  Stop adding immediately on first signal.
  Move freed capital to BTC + stablecoins.
  No hedging instruments (no options or inverse tokens per constitution).
```

---

## BLOCK 4 — STATUS TRACKER (update weekly)

```
Date       | Scenario | Key signal                       | Action
-----------|----------|----------------------------------|----------
2026-03-06 | Base     | Position start, pilot 6%         | Bought
_________  | ___      | ___                              | ___
```

> **Main question at each update:** did the scenario change?
> Base → Bull: add. Base → Bear: stop adding, review.

---

## BLOCK 5 — ALERTS / MONITORING (position follow-up)

> Without alerts the assistant "dies" after a one-off analysis.
> With alerts — the human sleeps calmly.

### Price alerts (P)

| # | Level | Type | Action | Status |
|---|---|---|---|---|
| P1 | $_____ | ☐ Stop ☐ Take ☐ Support ☐ Resistance ☐ Scenario | | ☐ Act. ☐ Triggered |
| P2 | $_____ | | | |
| P3 | $_____ | | | |

### On-chain / Fundamental alerts (F)

| # | Metric | Threshold | Action | When |
|---|---|---|---|---|
| F1 | NSM: ___ (e.g. DeFi TVL) | < $___ | Review thesis | weekly check |
| F2 | Tokenomics: net issuance | > +___% annually | Review tokenomics | monthly |
| F3 | Funding rates | > 0.05%/8h for 7d | Check euphoria, trim? | daily |

### Event alerts (E)

| # | Event | Date | Before | After |
|---|---|---|---|---|
| E1 | Major protocol upgrade | | Review size? | Update 06 + 08 |
| E2 | Regulatory ruling | | Monitor closely | /triage_news |
| E3 | Large token unlock (if any) | | Check selling pressure | Update snapshot |

### Update protocol on trigger

| Event | Update | Priority |
|---|---|---|
| Price alert | 08 → check scenario | High |
| On-chain alert (TVL/issuance) | 06 + 08 → review thesis | High |
| Event (upgrade/hack) | 06 + 08 + 07 | High |
| Weekly check-up | 04 + 07 + 10 + alerts | Mandatory |
| BTC regime changed (crosses 200 DMA) | 07 → all 08 → all stops | Critical |

### Required minimum:
- Live position: **1 price alert (P) + 1 on-chain metric alert (F)**
- Ready candidate: **1 entry price level (P)**
- Without alerts = **"⚠️ Unmonitored"** in 04_snapshot

---

*Version 1.0 · Crypto adaptation. Replaced: company financials → on-chain metrics. Replaced: earnings events → protocol upgrades/regulatory events. Added: BTC cycle triggers, funding rate alerts, ETF flow triggers.*
