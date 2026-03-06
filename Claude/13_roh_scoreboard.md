# 13_roh_scoreboard.md — ROH Scoreboard (Return On Habit) v2

## PURPOSE

Investor discipline metric. Measures process repeatability. ROH is "return on habit": returns on habit. Without discipline — no result. The "sleep peacefully" goal is achieved not by price forecast, but by a repeatable process.

## WHEN TO USE

- Weekly: as part of weekly check-up (filled in 10_decision_journal)
- On command `ROH_REPORT`
- Automatically: assistant checks ROH when attempting new entry

---

## ROH FORMULA (10 points)

No psychology, no philosophy — pure discipline.

| # | What we check | Points |
|---|---|---|
| 1 | **Snapshot updated** — 04 updated this week | 0 or 1 |
| 2 | **Context updated** — 07 updated this week | 0 or 1 |
| 3 | **All actions recorded** — all weekly decisions in 10_journal | 0 or 1 |
| 4 | **0 Constitution violations** — no limit/ban breaches | 0 or 1 |
| 5 | **Risk within limits** — Heat/NBE/autopilot observed | 0 or 1 |
| 6 | **Quality Gates observed** — all entries through 12 (or no entries = auto-PASS) | 0 or 1 |
| 7 | **Active practice** — at least 1 of: TRIAGE_NEWS / RED_TEAM / BLACK_BOX / AUDIT_NUMBERS | 0 or 1 |
| 8 | **Pipeline current** — candidate statuses in 04 updated | 0 or 1 |
| 9 | **Alerts reviewed** — alerts in 08 reviewed, stale ones updated | 0 or 1 |
| 10 | **Emotional hygiene** — didn't trade in trigger (from 02). Observed info diet | 0 or 1 |

**ROH = __/10**

### Alternative simplified formula (5 × 2 points)

For Lite mode or beginners — simplified version can be used:

| # | Item | Points |
|---|---|---|
| 1 | Updated Snapshot (04) | 0 or 2 |
| 2 | Updated Context (07) | 0 or 2 |
| 3 | All actions recorded in journal | 0 or 2 |
| 4 | 0 Constitution violations | 0 or 2 |
| 5 | Risk within limits (Heat/NBE) | 0 or 2 |

Total: 0–10. Minimum set — same scale.

---

## THRESHOLDS AND REACTION

| ROH | Zone | Action |
|---|---|---|
| **8–10** | 🟢 Excellent | Continue. Can raise mode (Lite→Standard, Standard→Pro) |
| **6–7** | 🟡 Attention | Show what was missed. 1–2 specific recommendations. Mode unchanged |
| **4–5** | 🟠 Problem | **Automatic Lite** for next week. No new entries. Accompaniment only |
| **0–3** | 🔴 Stop | **Lite + full pause.** Stops and emergency management only |

> **Unified standard** (synced with 04_snapshot and 02_passport v2.1):
> 🟢 Green zone = ROH ≥ 8. Below 6 → Lite activates automatically.

---

## TWO-WEEK RULE

ROH < 5 **twice in a row** → assistant initiates structured conversation:

```
⚠️ ROH below 5 for the second week in a row.

This is not a failure — it's a signal that the process is too heavy right now.

1. What's blocking the most?
   ☐ No time  ☐ Too complex  ☐ Don't see the benefit  ☐ Other

2. What can be simplified?
   - Reduce candidates in pipeline (current: ___)
   - Switch to Lite (if not already)
   - Cut down info diet
   - Take a 1–2 week pause (alerts and stops only)

3. What do you definitely want to keep?
```

---

## `ROH_REPORT` COMMAND OUTPUT FORMAT

```
╔══════════════════════════════════════════════╗
  ROH REPORT — week [DATE]
  
  ROH: __/10  Zone: 🟢/🟡/🟠/🔴
  
  ✅ Done:
  • ___
  • ___
  
  ❌ Missed:
  • ___
  • ___
  
  📊 Trend (4 weeks): __ → __ → __ → __
  
  💡 Recommendations for next week:
  1. ___
  2. ___
  
  Mode for next week: [Lite / Standard / Pro]
╚══════════════════════════════════════════════╝
```

---

## ROH TRACKER (history)

| Week | ROH | Zone | What missed | 1 improvement |
|---|---|---|---|---|
| _________ | __/10 | 🟢🟡🟠🔴 | | |
| _________ | __/10 | 🟢🟡🟠🔴 | | |
| _________ | __/10 | 🟢🟡🟠🔴 | | |
| _________ | __/10 | 🟢🟡🟠🔴 | | |

---

## RULES

1. ROH is calculated WEEKLY. Skip = automatic ROH = 0.
2. ROH — diagnostics, not punishment. Goal: find "what's blocking" and simplify.
3. Assistant NEVER criticizes for low ROH. Facts + recommendations only.
4. ROH is recorded in 10_journal and 04_snapshot (discipline scoreboard).
5. If item not applicable for the week (no news to triage) — auto-PASS.
6. User can use full (10 items) or simplified (5 × 2) formula.

---

*Version 2.1 · Thresholds synced with 04_snapshot and 02_passport: 🟢 ≥8, 🟡 6–7, 🟠 4–5, 🔴 0–3.*
