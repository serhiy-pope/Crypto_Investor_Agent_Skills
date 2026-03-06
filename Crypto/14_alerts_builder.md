# 14_alerts_builder.md — Crypto Alerts Building and Protocol v1.0

## PURPOSE

Turns triggers from 08_scenario_map into a living follow-up system. Without alerts the assistant "dies" after a one-off analysis. With alerts — the human sleeps calmly, because they know: "if something happens — I have a pre-written rule".

**Crypto note:** Alerts are even more critical than in equities because crypto markets operate 24/7 and moves can be extreme within hours.

## WHEN TO USE

- After filling 08_scenario_map (required next step)
- On "set up alerts" from 09_final_report
- Weekly: relevance check as part of weekly review
- When any alert triggers

---

## ALERT TYPES

### 1. Price — P

| Subtype | When to set | Required? |
|---|---|---|
| **Stop-loss** | Always. Every Live YELLOW/ORANGE position | YES |
| **Take-profit / Trim** | When target price from valuation exists | Recommended |
| **Support level** | For trend monitoring (EMA200, key levels) | Optional |
| **Entry level** | For Ready candidates | YES (for Ready) |
| **Scenario trigger** | Tied to Bull/Base/Bear zones from 08 | Recommended |
| **Euphoria trim** | Price ×2 or ×3 from entry — partial profit | Recommended |

### 2. On-chain / Fundamental — F

| Subtype | When to set | Check frequency |
|---|---|---|
| **NSM alert** | When North Star Metric is outside expectations | Weekly |
| **TVL threshold** | When DeFi TVL falls below threshold | Weekly (DeFiLlama) |
| **Tokenomics** | Net issuance turns inflationary | Monthly |
| **Funding rates** | Perpetual funding > 0.05%/8h for 7+ days | Daily |
| **Exchange netflow** | Massive inflow (selling pressure signal) | Weekly (Glassnode) |
| **Unlock alert** | Token unlock >5% supply in next 30 days | Monthly |

### 3. Event alerts (Calendar) — E

| Subtype | When to set | Required? |
|---|---|---|
| **Protocol upgrade** | Major hard fork, upgrade | YES (every GREEN) |
| **Regulatory hearing** | Known dates (SEC, EU, CFTC) | YES if relevant |
| **Token unlock** | Scheduled vesting unlocks | YES if any |
| **ETF flow report** | Weekly institutional flow data | Recommended |
| **BTC halving / cycle** | Pre-set cycle milestones | Once |

---

## BUILDING ALERTS (step by step)

### Step 1: Gather data

```
Token: ________
Current price: $________
BTC price: $________
Position: ☐ Live  ☐ Ready  ☐ Research

From 08_scenario_map:
- Bull target: $________
- Base target: $________
- Bear target: $________
- Stop-loss (YELLOW): $________ / ___% from entry
- Thesis invalidation (GREEN): event: ________

From 06_asset_card:
- NSM: ________________  Current value: ________  Threshold: ________
- Key metric: ______  Threshold: ________
- Next known unlock: ________ (date + % supply)

Upcoming events:
- Protocol upgrade: ________
- Regulatory: ________
- Unlock: ________

Custody:
- Exchange alerts available on: ________
- On-chain alert tool: ________  (Glassnode / Nansen / DeFiLlama)
```

### Step 2: Fill the alerts table

```
## ALERTS FOR [TOKEN] (creation date: ________)

### Price (P)
| # | Level | Type | Action | Status |
|---|---|---|---|---|
| P1 | $____ | Stop-loss | Review / partial exit / full exit | ☐ Active |
| P2 | $____ | Scenario (Bear zone) | RED_TEAM + check scenario | ☐ Active |
| P3 | $____ | Scenario (Bull zone) | Consider partial trim (30%) | ☐ Active |
| P4 | $____ | Euphoria trim | Trim 30–50% at 2–3x entry | ☐ Active |

### On-chain / Fundamental (F)
| # | Metric | Threshold | Action | Check |
|---|---|---|---|---|
| F1 | NSM: _______ | _______ | Review thesis | weekly |
| F2 | Funding rate | > 0.05%/8h × 7d | /redteam — euphoria check | daily |
| F3 | TVL: _______ | < $___ | Scenario Base→Bear? | weekly |
| F4 | Issuance | > +2% annually | Tokenomics alert | monthly |

### Event (E)
| # | Event | Date | Before event | After event |
|---|---|---|---|---|
| E1 | Protocol upgrade | ____ | −2 wk: review size | Update 06 + 08 |
| E2 | Token unlock | ____ | −4 wk: check selling pressure | Monitor price |
| E3 | Regulatory | ____ | Monitor closely | /triage_news |
```

### Step 3: Insert into 08_scenario_map

Copy the table into the ALERTS/MONITORING block of the corresponding scenario map.

---

## WHEN AN ALERT TRIGGERS

Algorithm (1 screen, very clear):

```
1. Identify type of triggered alert: P / F / E
2. Check: did the scenario in 08 change?
   - Moved from Base to Bear? From Base to Bull?
3. If scenario changed → update 08, and 06 and 07 if needed
4. Offer action options (NOT a command):
   ☐ Nothing (alert informational)
   ☐ Review size
   ☐ Review thesis (RED_TEAM)
   ☐ Partial / full exit
   ☐ Update stop-loss
   ☐ Update alerts
5. Record in 10_decision_journal
6. Update alert status: Active → Triggered
```

---

## UPDATE PROTOCOL

| Event | What to update | Priority |
|---|---|---|
| Price alert triggered | 08 → check scenario | High |
| On-chain alert (TVL/issuance) | 06 + 08 → review thesis | High |
| Event alert (upgrade/regulatory) | 06 + 08 + 07 | High |
| Weekly check-up | 04 + 07 + 10 + check all alerts | Mandatory |
| BTC regime changed (crosses 200 DMA) | 07 → all 08 → all stop-losses | Critical |
| Major hack/exploit on ANY protocol | 06 + 08 + 07 → emergency review | Critical |

---

## REQUIRED MINIMUM

| Position type | Required alerts |
|---|---|
| **Live GREEN** | 1 on-chain metric alert (F) + 1 protocol upgrade event (E) |
| **Live YELLOW** | 1 stop-loss (P) + 1 scenario alert (P) + 1 on-chain metric (F) |
| **Live ORANGE** | 1 stop-loss (P) — full loss expected, but track catalyst |
| **Ready** (candidate) | 1 entry price level (P) |
| **Research** | — (alerts set when moving to Ready) |

- Position without alerts = **"⚠️ Unmonitored"** in 04_snapshot.
- Alerts reviewed WEEKLY (counts in ROH).
- On BTC regime change → review ALL stop-losses.

---

## "CALM PLAYBOOK" (template for each key position)

For each key position — 1 card:

```
[TOKEN]: __________

What I do every week (5 min):
→ Check P alerts, check on-chain NSM

What I do at −20%:
→ [specific action from 08, pre-written]

What I do at −40%:
→ [specific action, usually: check thesis, RED_TEAM, decide by autopilot]

What breaks the thesis (capitulation):
→ [from 06: specific event/metric → exit unconditionally]

My alerts:
→ Stop (Y): $___  |  Bull trim: $___  |  NSM threshold: ___  |  Next unlock: ___
```

---

## CRYPTO-SPECIFIC ALERT TOOLS

**Suggested platforms for setting alerts:**
- **Price alerts:** TradingView, Binance, exchange apps
- **On-chain alerts:** Glassnode (funding, flows), Nansen (whale tracking), DeFiLlama (TVL)
- **Protocol events:** DeBank, protocol Discord/governance forums
- **Calendar events:** CryptoWisdom, CoinMarketCal

---

## RULES

1. Assistant does NOT execute alerts automatically. Only notifies and offers options.
2. Every Live position MUST have the minimum set of alerts.
3. Alerts are "pre-written rules". Their point: when the event happens, you already know what to do.
4. No alerts = no calm = no follow-up.
5. Crypto note: don't set alerts that fire every hour — that leads to overtrading. Weekly on-chain checks are usually sufficient for GREEN positions.
