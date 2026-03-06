# 14_alerts_builder.md — Alerts Building and Protocol v2

## PURPOSE

Turns triggers from 08_scenario_map into a living follow-up system. Without alerts the assistant "dies" after a one-off analysis. With alerts — the human sleeps calmly, because they know: "if something happens — I have a pre-written rule".

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
| **Stop-loss** | Always. Every Live position | YES |
| **Take-profit** | When target price from valuation exists | Recommended |
| **Support level** | For trend monitoring | Optional |
| **Entry level** | For Ready candidates | YES (for Ready) |
| **Scenario trigger** | Tied to Bull/Base/Bear zones from 08 | Recommended |

### 2. Fundamental — F

| Subtype | When to set | Check frequency |
|---|---|---|
| **NSM alert** | When North Star Metric is outside expectations | After each earnings |
| **Margin** | When margin falls below threshold | After each earnings |
| **Debt load** | When Debt/EBITDA rises | After each earnings |
| **Earnings quality** | When NOA / ESCORE deteriorates | After each earnings |

### 3. Event alerts (Calendar) — E

| Subtype | When to set | Required? |
|---|---|---|
| **Earnings** | 2 weeks before report | YES (every Live) |
| **Guidance / Investor Day** | When on calendar | Recommended |
| **Macro event** | Fed, elections, regulatory decisions | Case by case |
| **Option expiration** | If option positions exist | YES (if any) |

---

## BUILDING ALERTS (step by step)

### Step 1: Gather data

```
Ticker: ________
Current price: $________
Position: ☐ Live  ☐ Ready  ☐ Research

From 08_scenario_map:
- Bull target: $________
- Base target: $________
- Bear target: $________
- Stop-loss: $________
- Thesis invalidation (capitulation): $________ / event: ________

From 06_company_card:
- NSM: ________________  Current value: ________  Threshold: ________
- Key margin: ______  Threshold: ________
- Debt/EBITDA: ______  Threshold: ________

Upcoming events:
- Earnings: ________
- Other: ________
```

### Step 2: Fill the alerts table

```
## ALERTS FOR [TICKER] (creation date: ________)

### Price (P)
| # | Level | Type | Action | Status |
|---|---|---|---|---|
| P1 | $____ | Stop-loss | Review / partial exit / full exit | ☐ Active |
| P2 | $____ | Take-profit | Partial lock-in ___% | ☐ Active |
| P3 | $____ | Scenario (Bear zone) | RED_TEAM + check scenario | ☐ Active |
| P4 | $____ | Scenario (Bull zone) | Consider partial lock-in | ☐ Active |

### Fundamental (F)
| # | Metric | Threshold | Action | Check |
|---|---|---|---|---|
| F1 | NSM: _______ | _______ | Review thesis | after earnings |
| F2 | Margin: ______ | < ___% | Downgrade class? | after earnings |
| F3 | Debt/EBITDA | > ___x | RED_TEAM | after earnings |

### Event (E)
| # | Event | Date | Before event | After event |
|---|---|---|---|---|
| E1 | Earnings | ____ | −2 wk: review size, hedge? | Update 06 + 08 |
| E2 | _________ | ____ | ____________ | ____________ |
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
| Fundamental alert | 06 + 08 → review thesis | High |
| Event alert (earnings) | 06 + 08 + 07 | High |
| Weekly check-up | 04 + 07 + 10 + check all alerts | Mandatory |
| Macro regime changed | 07 → all 08 → ALL stop-losses | Critical |

---

## REQUIRED MINIMUM

| Position type | Required alerts |
|---|---|
| **Live** (in portfolio) | 1 stop-loss (P) + 1 event alert for nearest earnings (E) |
| **Ready** (candidate) | 1 entry price level (P) |
| **Research** | — (alerts set when moving to Ready) |

- Position without alerts = **"⚠️ Unmonitored"** in 04_snapshot.
- Alerts reviewed WEEKLY (counts in ROH).
- On Macro regime change → review ALL stop-losses.

---

## "CALM PLAYBOOK" (template for final homework)

For each key position — 1 card:

```
[TICKER]: __________

What I do every week (5 min):
→ Check alerts P1–P3, watch price

What I do at −10%:
→ [specific action from 08, pre-written]

What I do at −20%:
→ [specific action, usually: check thesis, RED_TEAM, decide by autopilot]

What breaks the thesis (capitulation):
→ [from 06: specific event/metric → exit unconditionally]

My alerts:
→ Stop: $___  |  Take: $___  |  Earnings: ____
```

---

## RULES

1. Assistant does NOT execute alerts automatically. Only notifies and offers options.
2. Every Live position MUST have the minimum set of alerts.
3. Alerts are "pre-written rules". Their point: when the event happens, you already know what to do (no improvising and no panic).
4. No alerts = no calm = no follow-up.
