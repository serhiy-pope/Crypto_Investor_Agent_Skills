# Portfolio Snapshot — Crypto
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
Base (currency): USD
Portfolio size (NAV): $___
Agent working mode: Lite / Standard / Pro (current: ___)

BTC price at snapshot: $___
ETH price at snapshot: $___

Important event in the next 7–14 days (major unlock, regulatory hearing, halving, hard fork): ___
```

---

## BLOCK 1 — PORTFOLIO STRUCTURE

```
BTC (reserve/core):     ___%
ETH (core L1):          ___%
Other GREEN (L1/L2):    ___%
YELLOW (protocols/alts): ___%
ORANGE (speculative):   ___%
Stablecoins / Cash:     ___%

Total:                  100%

Portfolio goal (1 line): ___
BTC cycle position (estimated): Accumulation / Early Bull / Mid Bull / Late Bull / Bear
```

---

## BLOCK 2 — POSITIONS

| Ticker | Class | Weight,% | Entry price | Current price | P&L,% | Stop / Invalidation | UsedRisk,% | Custody | Alerts? | Status |
|---|---|---:|---:|---:|---:|---|---:|---|---|---|
| `___` | `G/Y/O` | `___` | `$___` | `$___` | `___` | `___` | `___` | `CEX/Cold/Hot` | `yes/no` | `OK / Watch / Review` |

**Statuses:**
- `OK` — everything is according to plan
- `Watch` — attention needed (close to stop, regime/trend changed, unlock approaching)
- `Review` — thesis/size must be reconsidered

⚠️ Position without alerts = **«Unmanaged»** — mark and configure via `14_alerts_builder`.
⚠️ Position without custody annotation = **«Custody undefined»** — must be resolved.

---

## BLOCK 3 — SUMMARY METRICS (limits)

```
Directional Heat (YELLOW risk): ___%   (limit: ___%)

|MDD| from High Watermark (portfolio): ___%   (limit: ≤ 30%)
Time-to-Recovery to HWM:           ___ months (limit: ≤ 12 months)

Max token concentration: ___% (token: ___)
Max sector concentration: ___% (sector: ___)
Single CEX exposure: ___% (exchange: ___)
Hot wallet exposure: ___% (limit: ≤ 20%)
Cold storage: ___%

Stablecoins: ___% (minimum floor: 10%)

Main skew/risk of the week (1 line): ___
```

### Quick formulas

**Heat:** UsedRisk per position = Weight × Stop_distance. Total Heat = Σ UsedRisk (YELLOW only).
**BTC correlation:** all altcoins are highly correlated to BTC; treat entire portfolio as one BTC-correlated exposure unless specifically hedged.

---

## BLOCK 4 — IDEA INBOX (idea triage and limit)

> This is where "ideas live" without turning into trades.

### Limits (if not specified in passport)
```
Raw ideas per day: ≤ 3
Into analysis per week: ≤ 2
Into capital per month: ≤ 1
Active candidates: ≤ 5
Total in Inbox: ≤ 10
```

### Inbox table

| Idea/Token | Type | Source/reason | Status | Next trigger | Review date |
|---|---|---|---|---|---|
| `___` | `core/protocol/narrative/speculative` | `___` | `Noise / Watch / Action` | `___` | `____-__-__` |

**Rule:** if Inbox is full — first delete/freeze 1–3 old ideas, then add a new one.

---

## BLOCK 5 — PIPELINE (entry candidates)

| # | Token | Status | Idea source | Transition condition | Date added | Date updated |
|---|---|---|---|---|---|---|
| 1 | | ☐ Backlog ☐ Research ☐ Ready ☐ → Live | | | | |
| 2 | | ☐ Backlog ☐ Research ☐ Ready ☐ → Live | | | | |
| 3 | | ☐ Backlog ☐ Research ☐ Ready ☐ → Live | | | | |
| 4 | | ☐ Backlog ☐ Research ☐ Ready ☐ → Live | | | | |
| 5 | | ☐ Backlog ☐ Research ☐ Ready ☐ → Live | | | | |

**Statuses:** Backlog (frozen) → Research (fill 06+08) → Ready (Gates passed, waiting for entry) → Live (in portfolio)

**Positions under observation:**
```
Token | Reason | Action when: ___
```

**Open questions:** ___

---

## BLOCK 6 — CUSTODY MAP

> Critical for crypto — must be updated after every custody change.

```
Cold storage (hardware wallet):  ___% ($___) → Tokens: ___
Hot wallet (software):           ___% ($___) → Tokens: ___
CEX 1 (___):                     ___% ($___) → Tokens: ___
CEX 2 (___):                     ___% ($___) → Tokens: ___
DeFi protocols (deployed):       ___% ($___) → Protocols: ___
Staking/locked:                  ___% ($___) → Tokens/duration: ___
```

⚠️ Single CEX > 20% of portfolio = **«Concentration Warning»** — reduce or diversify.

---

## BLOCK 7 — DISCIPLINE DASHBOARD

| Metric | Value | Status |
|---|---|---|
| ROH (week) | __/10 | ☐ ≥8 🟢  ☐ 6–7 🟡  ☐ <6 → Lite |
| Protocol Compliance | __% | (trades via QPTA+Gates / total trades) |
| Decisions this week | __/3 max | |
| Journal filled? | ☐ Yes  ☐ No | (No → new entries blocked) |
| Heat current | __% / __% max | |
| \|MDD\| from HWM | ___% | ☐ ≤30% 🟢  ☐ 30–50% 🟡  ☐ >50% 🔴 |
| Time-to-Recovery | ___ months | ☐ ≤12 months 🟢  ☐ >12 months 🟡 |
| Hot wallet % | ___% | ☐ ≤20% 🟢  ☐ >20% 🔴 |
| Stablecoin reserve | ___% | ☐ ≥10% 🟢  ☐ <10% 🔴 |

### Happiness Index (summary row)

| # | Need | Metric | Actual | Threshold | Status |
|---|---|---|---|---|---|
| 1 | Sleep | \|MDD\| + Time-to-Recovery to HWM | ___% / ___ months | ≤30% / ≤12 months | 🟢/🟡/🔴 |
| 2 | Progress | Return vs Benchmark (BTC from Passport) | ___% | > BTC benchmark | 🟢/🟡/🔴 |
| 3 | Confidence | Winrate + Profit Factor¹ | ___% / ___ | ≥40% / ≥1.5 | 🟢/🟡/🔴 |
| 4 | Control | Protocol Compliance + ROH | ___% / __/10 | ≥80% / ≥8 | 🟢/🟡/🔴 |
| 5 | Security | Hot wallet % + CEX concentration | ___% / ___% | ≤20% / ≤20% | 🟢/🟡/🔴 |

¹ Only if trade statistics exist (YELLOW/ORANGE). For GREEN — alternative: % of quarters outperforming BTC benchmark.

---

## HOW TO UPDATE THIS FILE

1) Every Sunday: update prices, P&L, statuses, metrics (Heat/concentrations/custody), ROH
2) After every trade: update positions table + recalculate metrics
3) After check-up: update Idea Inbox and pipeline
4) After custody change: update Block 6 immediately
5) Upload updated version to Project (**old one — move to /archive, do not delete**)

---

*Version 1.0 · Crypto adaptation. Added: custody map (Block 6), BTC cycle position, stablecoin floor, single CEX concentration limit, crypto-specific Happiness Index.*
