# Portfolio Snapshot
### Module 1 · Update weekly + after every trade

---

> **How to use**
> - This is the portfolio "control panel".
> - The Agent makes decisions only based on an up-to-date snapshot.
> - Snapshot not updated → the Agent works with outdated data (garbage in = garbage out).

---

## BLOCK 0 — HEADER / FRESHNESS

```
Snapshot date: ____-__-__
Next scheduled update: ____-__-__
Base (currency): ___
Portfolio size (NAV): $___
Agent working mode: Lite / Standard / Pro (current: ___)

Important event in the next 7–14 days (earnings, tax, relocation, liquidity): ___
```

---

## BLOCK 1 — PORTFOLIO STRUCTURE

```
Stocks  (equity): ___%
Bonds: ___%
Cash / money market: ___%
Other (gold/crypto/…): ___%

Portfolio goal (1 line): ___
```

---

## BLOCK 2 — POSITIONS

| Ticker | Class | Weight,% | Entry price | Current price | P&L,% | Stop / Invalidation | UsedRisk,% | Alerts? | Status |
|---|---|---:|---:|---:|---:|---|---:|---|---|
| `___` | `G/Y/O` | `___` | `$___` | `$___` | `___` | `___` | `___` | `yes/no` | `OK / Watch / Review` |

**Statuses:**
- `OK` — everything is according to plan
- `Watch` — attention needed (close to stop, regime/trend changed)
- `Review` — thesis/size must be reconsidered

⚠️ Position without alerts = **«Unmanaged»** — mark and configure via `14_alerts_builder`.

---

## BLOCK 3 — SUMMARY METRICS (limits)

```
NBE (Normalized Beta Exposure): ___    (regime limit: ___)
Directional Heat (YELLOW risk): ___%   (limit: ___%)
Hedge Heat (ORANGE premium):   ___%   (limit: ___%)

|MDD| from High Watermark (portfolio): ___%   (limit: ≤ 15%)
Time-to-Recovery to HWM:           ___ months (limit: ≤ 6 months)

Max ticker concentration: ___%
Max sector concentration: ___%
FX‑exposure (non-base currency): ___% (limit: ___%)

Main skew/risk of the week (1 line): ___
```

### Quick formulas

**Heat:** UsedRisk per position = Weight × Stop_distance. Total Heat = Σ UsedRisk.
**NBE:** NBE = Σ (Weight × Beta), including shorts and hedges.

---

## BLOCK 4 — IDEA INBOX (idea triage and limit)

> This is where “ideas live” without turning into trades.

### Limits (if not specified in passport)
```
Raw ideas per day: ≤ 3
Into analysis per week: ≤ 2
Into capital per month: ≤ 1
Active candidates: ≤ 5
Total in Inbox: ≤ 10
```

### Inbox table

| Idea/Ticker | Type | Source/reason | Status | Next trigger | Review date |
|---|---|---|---|---|---|
| `___` | `core/trade/hedge/theme` | `___` | `Noise / Watch / Action` | `___` | `____-__-__` |

**Rule:** if Inbox is full — first delete/freeze 1–3 old ideas, then add a new one.

---

## BLOCK 5 — PIPELINE (entry candidates)

| # | Ticker | Status | Idea source | Transition condition | Date added | Date updated |
|---|---|---|---|---|---|---|
| 1 | | ☐ Backlog ☐ Research ☐ Ready ☐ → Live | | | | |
| 2 | | ☐ Backlog ☐ Research ☐ Ready ☐ → Live | | | | |
| 3 | | ☐ Backlog ☐ Research ☐ Ready ☐ → Live | | | | |
| 4 | | ☐ Backlog ☐ Research ☐ Ready ☐ → Live | | | | |
| 5 | | ☐ Backlog ☐ Research ☐ Ready ☐ → Live | | | | |

**Statuses:** Backlog (frozen) → Research (fill 06+08) → Ready (Gates passed, waiting for entry) → Live (in portfolio)

**Positions under observation:**
```
Ticker | Reason | Action when: ___
```

**Open questions:** ___

---

## BLOCK 6 — DISCIPLINE DASHBOARD

| Метрика | Значение | Статус |
|---|---|---|
| ROH (week) | __/10 | ☐ ≥8 🟢  ☐ 6–7 🟡  ☐ <6 → Lite |
| Protocol Compliance | __% | (trades via QPTA+Gates / total trades) |
| Decisions this week | __/3 max | |
| Journal filled? | ☐ Yes  ☐ No | (No → new entries blocked) |
| Heat current | __ bp / __ bp max | |
| NBE current | __ / __ max | |
| \|MDD\| from HWM | ___% | ☐ ≤15% 🟢  ☐ 15–20% 🟡  ☐ >20% 🔴 |
| Time-to-Recovery | ___ months | ☐ ≤6 months 🟢  ☐ >6 months 🟡 |

### Happiness Index (summary row)

| # | Need | Metric | Actual | Threshold | Status |
|---|---|---|---|---|---|
| 1 | Sleep | \|MDD\| + Time-to-Recovery to HWM | ___% / ___ months | ≤15% / ≤6 months | 🟢/🟡/🔴 |
| 2 | Progress | Return vs Benchmark (from Passport) | ___% | > Benchmark | 🟢/🟡/🔴 |
| 3 | Confidence | Winrate + Profit Factor¹ | ___% / ___ | ≥40% / ≥1.5 | 🟢/🟡/🔴 |
| 4 | Control | Protocol Compliance + ROH | ___% / __/10 | ≥80% / ≥8 | 🟢/🟡/🔴 |

¹ Only if trade statistics exist (YELLOW/ORANGE). For GREEN — alternative: % of positive quarters.

---

## HOW TO UPDATE THIS FILE

1) Every Sunday: update prices, P&L, statuses, metrics (NBE/Heat/concentrations), ROH
2) After every trade: update positions table + recalculate metrics
3) After check-up: update Idea Inbox and pipeline
4) Upload updated version to Project (**old one — move to /archive, do not delete**)

---

*Version 2.1 · Added: |MDD| and Time-to-Recovery in BLOCK 3, ROH threshold corrected (≥8 🟢), added “Happiness Index” in BLOCK 6.*
