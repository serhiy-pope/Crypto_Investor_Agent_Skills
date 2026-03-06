# Scenario Map by Ticker
### Modules 1–3 · Bear / Base / Bull · Action branches · Alerts

---

> **How to use**
> Filled when opening a position — before entry, not after.
> Three scenarios describe possible paths for the thesis to develop, not price forecasts.
> Probabilities must sum to 100% — this disciplines thinking.
> Update after each quarterly report or when triggers change.
> Main value: when the market falls, you know in advance — is it Base or Bear?

---

## HEADER

```
Ticker: ___
Date: ____-__-__
Price now: $___
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

What happens to the business: ___
Key assumptions: 1) ___  2) ___  3) ___
Financials in 12 months: Revenue $___  Margin ___%  FCF $___
Multiple: ___x → Price: $___  Potential: +___%

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

### Example: ASML

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
🟢 BULL — "AI supercycle accelerates EUV"
Probability: 30%

AI chip demand forces TSMC and Samsung to accelerate capex.
Backlog grows above €45B. ASML raises guidance twice in a year.

Assumptions: 1) TSMC capex to $38–40B  2) No export expansion
3) High-NA EUV receives first commercial orders from Intel

Revenue: €33B (+17%) | Gross Margin: 53–54% | FCF: ~€7.5B
Multiple: 35x P/E → Price: $950 → Potential: +32%

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
🟡 BASE — "Steady growth on plan"
Probability: 50%

ASML delivers guidance €30–35B. Backlog stable €36–40B.
Gross margin 51–52%. China limited, offset by growth in other regions.

Assumptions: 1) TSMC capex ~$32B ±10%  2) Restrictions don't expand
3) Macro neutral / moderately positive

Revenue: €30B (+6%) | Gross Margin: 51–52% | FCF: ~€6.5B
Multiple: 30x P/E → Price: $820 → Potential: +14%

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
🔴 BEAR — "Cycle turns"
Probability: 20%

Foundry capex cut amid AI demand slowdown or recession.
Backlog below €30B. ASML cuts guidance. Restrictions expanded.

Assumptions: 1) TSMC capex −20–25% y/y  2) DUV restrictions expanded
3) Global recession

Revenue: €24B (−15%) | Gross Margin: 47–48% | FCF: ~€4B
Multiple: 22x P/E → Price: $520 → Potential: −28%
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

EV = $950×30% + $820×50% + $520×20% = $285 + $410 + $104 = $799 (+11%)
```

---

## BLOCK 2 — TRANSITION TRIGGERS

### Template
```
BASE → BULL: ✓ ___  ✓ ___
BASE → BEAR: ✗ ___  ✗ ___
BEAR → INVALIDATION: ✗ ___ → immediate review
```

### Example: ASML
```
BASE → BULL:
  ✓ Backlog grows above €42B at any quarter end
  ✓ TSMC raises capex guidance above $36B
  ✓ ASML raises annual guidance

BASE → BEAR:
  ✗ Backlog below €32B for two consecutive quarters
  ✗ Gross margin < 49%
  ✗ TSMC/Samsung cut capex >20% y/y
  ✗ New restrictions close >10% of revenue

BEAR → INVALIDATION:
  ✗ Backlog < €25B → visibility thesis broken
  ✗ Real EUV competitor emerges
  ✗ ROIC < 18% for two consecutive quarters
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

### Example: ASML
```
On BULL:
  To 10% (max GREEN). Add on first Bull trigger.
  If drift >15% — trim in steps of 1%/month.

On BASE (current):
  5% (pilot). Hold, don't add until Bull triggers.
  If drift >12% — trim to 10%.

On BEAR:
  Reduce to 2–3% on first two Bear signals.
  Stop adding immediately on first signal.
  Hedge: ORANGE protective put on Bear confirmation.
```

---

## BLOCK 4 — STATUS TRACKER (update weekly)

```
Date       | Scenario | Key signal                      | Action
-----------|----------|----------------------------------|----------
2025-02-16 | Base     | Position start, pilot 5%        | Bought
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

### Fundamental alerts (F)

| # | Metric | Threshold | Action | When |
|---|---|---|---|---|
| F1 | NSM: ___ | | | after earnings |
| F2 | Margin | < ___% | | after earnings |
| F3 | Debt/EBITDA | > ___x | | after earnings |

### Event alerts (E)

| # | Event | Date | Before | After |
|---|---|---|---|---|
| E1 | Earnings | | Review size? | Update 06 + 08 |
| E2 | Macro (Fed) | | Don't enter within 3 days | /triage_news |

### Update protocol on trigger

| Event | Update | Priority |
|---|---|---|
| Price alert | 08 → check scenario | High |
| Fundamental | 06 + 08 → review thesis | High |
| Event (earnings) | 06 + 08 + 07 | High |
| Weekly check-up | 04 + 07 + 10 + alerts | Mandatory |
| Macro regime changed | 07 → all 08 → all stop-losses | Critical |

### Required minimum:
- Live position: **1 stop (P) + 1 nearest earnings event (E)**
- Ready candidate: **1 entry price level (P)**
- Without alerts = **"⚠️ Unmonitored"** in 04_snapshot

---

*Version 3.0 · ASML examples restored (3 scenarios with numbers, EV, triggers, actions, tracker). Full ALERTS/MONITORING added.*
