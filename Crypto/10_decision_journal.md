# Decision Journal and Weekly Review — Crypto
### Module 3 · Living memory of portfolio · Update every week

---

> **How to use**
> This is the only system file that *grows* over time — everything else gets updated.
> Decision journal: one row per action (bought, sold, added, closed).
> Weekly Review: new block every Sunday — do not delete old ones.
> Post-mortem: when closing a position or significant error.
> In a year this file will become your main teacher.

---

## BLOCK 0 — ROH (Return on Habit)

ROH — is not a "profit". It is a **process quality assessment**.

### Quick ROH‑score for the week (0–10)
```
+2  Weekly check-up was done
+2  Snapshot/Context updated on time
+2  All actions recorded in journal (no gaps)
+2  No trades outside constitution/limits
+2  If‑Then rules followed (no impulses)

−2  Trade without record
−2  Limit violation (Heat/concentration/custody)
−1  "Idea for dopamine" (Inbox full, but generating more)
−1  Traded based on Telegram/Twitter FOMO without triage
```

**Goal:** ROH ≥ 8/10 consistently.

### ROH thresholds and automation

| ROH | Zone | Action |
|---|---|---|
| **8–10** | 🟢 Excellent | Continue. Can raise mode |
| **6–7** | 🟡 Attention | Show what was missed. 1–2 recommendations |
| **4–5** | 🟠 Problem | Forced Lite. No new entries |
| **0–3** | 🔴 Stop | Lite + full pause. Stops and emergency management only |

**Two-week rule:** ROH < 5 twice → assistant initiates conversation: "What's blocking? Simplify? Remove candidates?"

Detailed formula — in `13_roh_scoreboard.md`.

---

## BLOCK 0B — PRE-ACTION CHECK (every Monday)

```
☐ Journal for last week filled? (No → accompaniment only)
☐ Last week's ROH ≥ 6? (No → Lite mode)
☐ Decision limit not exhausted?
☐ Snapshot (04) updated and < 7 days?
☐ Context (07) updated and < 7 days?
☐ BTC regime unchanged? (No → review all positions)
```

---

## PART 1 — DECISION LOG

> One row = one action. Fill right after execution.
> Honesty over polish — write as is.

```
Row format:
[DATE] | [TOKEN] | [ACTION] | [PRICE] | [SIZE] | [REASON] | [QPTA] | [CUSTODY] | [EMOTION*]

* Emotion: calm / doubt / FOMO / fear / confidence
  Fill honestly — this is diagnostics, not self-criticism.
* Custody: where stored (CEX name / cold / hot wallet)
```

| Date | Token | Action | Price | Size | Reason | QPTA | Custody | Emotion |
|---|---|---|---|---|---|---|---|---|
| `____-__-__` | `___` | `Bought/Sold/Added/Trimmed/Closed` | `$___` | `___%` | `___` | `✓/✗` | `___` | `___` |

> Tip: write not just "good protocol", but concretely:
> "QPTA passed, mid-bull cycle, pilot per plan" or
> "stop triggered, thesis not confirmed, closed without hesitation".

**Minimum record (if lack of time):**
1 row: **Date | Token | Action | Reason | QPTA? | Emotion**
If QPTA = ✗ → "impulsive trade" → counts in ROH.

**Unified archive row:**
```
[DATE] | [TOKEN] | [ACTION] | [CLASS] | [SIZE] | [UsedRisk] | [EV] | [THESIS] | [REVIEW TRIGGER]
```

---

## PART 2 — PORTFOLIO METRICS OVER TIME

> Fill once a week. In 3 months it will show patterns you'd otherwise miss.

| Week | NAV | YTD | vs BTC | Dir. Heat | Cash/Stable | BTC Price | Positions | Event |
|---|---|---|---|---|---|---|---|---|
| `____-__-__` | `$___` | `___%` | `+/−___%` | `___%` | `___%` | `$___` | `___` | `___` |

> Tip: "vs BTC" = your weekly return − BTC weekly return.
> In crypto, beating BTC is the real benchmark for active management.

---

## PART 3 — MINI DEAL CARD (before execution)

```
Date: ____-__-__  |  Token: ___  |  Action: ___  |  Class: G/Y/O

Plan:
- Entry: $___  |  Size: ___%  |  Horizon: ___
- BTC cycle position: ___
- Stop (Y) / Invalidation (G): ___
- Add trigger: ___  |  Exit trigger: ___
- Custody plan: ___% cold, ___% CEX (which exchange: ___)

Why now (1 sentence): ___
Risks (1–2): ___
```

---

## PART 4 — POST‑FACTUM (after execution or closure)

```
Actual price: $___  |  Actual size: ___%
Deviation from plan: yes/no (if yes — why)

Result (if closed):
  P&L: ___% / $___  |  Duration: ___ days
  vs BTC during period: +/−___%
  Per constitution: yes/no  |  Emotion (1 word): ___
  What I would do differently: ___
```

---

## PART 5 — WEEKLY CHECK‑UP

```
Week: ____-__-__ → ____-__-__

1) ROH‑score: ___/10  Zone: 🟢/🟡/🟠/🔴
2) BTC price change this week: +/−___%
3) Portfolio change this week: +/−___%
4) Most correct thing of the week: ___
5) Most dangerous thing of the week: ___
6) System violations: ___
7) What to improve (1 item): ___
```

### ROH TRACKER

| Week | ROH | Zone | What missed | 1 improvement |
|---|---|---|---|---|
| _________ | __/10 | 🟢🟡🟠🔴 | | |
| _________ | __/10 | 🟢🟡🟠🔴 | | |

---

## PART 6 — POST-MORTEM (on closure or significant error/success)

> Goal is not self-flagellation, but learning. The system improves only through review.

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
POST-MORTEM — [TOKEN] — [CLOSURE DATE]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

FACTS:
  Opened: ____-__-__  at $___  |  Closed: ____-__-__  at $___
  Result: +/−___% ($+/−___)  |  Duration: ___ days
  vs BTC during period: +/−___%
  Class: GREEN / YELLOW / ORANGE

WAS THE THESIS CORRECT?
  [ ] Yes — network/protocol behaved as expected
  [ ] Partially — thesis correct, but timing/size let down
  [ ] No — thesis proved wrong

WHAT WENT RIGHT: ___
  (Even a losing trade can be correctly executed.)

WHAT WENT WRONG: ___
  (Process error = violated a rule. Bad luck = followed the rule.)

CLASSIFICATION:
  [ ] Process error (violated constitution rule)
  [ ] Bad luck (followed rules, outcome unfavorable)
  [ ] Good luck (violated rules, but got lucky — dangerous!)
  [ ] Quality decision (followed rules, outcome favorable)

CRYPTO-SPECIFIC LESSONS:
  [ ] BTC cycle timing was wrong
  [ ] Overestimated protocol fundamentals
  [ ] Underestimated correlation to BTC
  [ ] FOMO entry at wrong cycle stage
  [ ] Ignored tokenomics risk (unlock, inflation)

PATCH-NOTE (new rule so it doesn't repeat):
  IF ___ THEN ___ BECAUSE ___

WHAT TO CHANGE IN THE SYSTEM:
  [ ] Nothing — system worked correctly
  [ ] Refine rule: ___
  [ ] Add trigger: ___
  [ ] Review limit: ___
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## PART 7 — QUARTERLY RETROSPECTIVE (once per quarter)

> 10 minutes once a quarter — the highest-return time investment.

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
QUARTERLY SUMMARY — Q___ ____
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

NUMBERS:
  Portfolio return: +/−___%
  BTC return (benchmark): +/−___%
  Alpha vs BTC:     +/−___%
  Trades: ___  |  Profitable: ___ (___%)  |  Losing: ___ (___%)
  Constitution violations: ___
  Average ROH for quarter: ___/10

MARKET CONTEXT:
  BTC cycle phase at start/end of quarter: ___
  Main narrative that drove performance: ___

TOP 3 LESSONS:
  1. ___
  2. ___
  3. ___

WHAT TO CHANGE FOR NEXT QUARTER:
  ___ (or "system works, no changes")

ONE PHRASE ABOUT THE QUARTER: ___
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

> **Main rule:** there is no "too small" event to record.
> Recorded → system remembers. Not recorded → system is blind.
> Journal discipline = portfolio discipline.

---

*Version 1.0 · Crypto adaptation. Added: custody column in decision log, BTC benchmark in metrics, crypto-specific post-mortem checklist, BTC cycle context in quarterly retrospective.*
