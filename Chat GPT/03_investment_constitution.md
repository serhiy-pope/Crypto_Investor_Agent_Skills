# Investment Constitution
### Module 1 · Anti-Ruin Rules · "The system is more important than opinion"

---

> **How to use**
> - This is the *law of the portfolio*. Any decision is compared against this file.
> - If a rule hinders a “beautiful idea” — the rule prevails.
> - Update rarely (1–2 times per year) and only after a sober retrospective, not under market pressure.

---

## HEADER

```
Date: ____-__-__
Version: 3.0
Base (currency): ___
Style: Saver / Investor / Speculator (proportions — see Passport)
```

---

## SECTION A — UNBREAKABLE PRINCIPLES

If an idea violates even one principle → immediate rejection, no discussion.

**A.1. Anti-Ruin / Sovereignty of Decisions**
Any positions, where they can force me to act, are prohibited: margin call, forced liquidation, uncovered obligations. A single point of failure (one asset / counterparty / market) capable of destroying the portfolio is forbidden.

**A.2. Validation, not emotions**
There is no absolute certainty. I resolve doubts with a pilot position + addition rules — not with belief.

**A.3. Business owner mindset**
I buy cash flows and value, not prices and emotions. Quality comes first: “cheap” does not justify “bad.” I buy only with a margin of safety.

**A.4. System + structural resilience**
Fundamentals = WHAT to buy. Market = WHEN. Plan = HOW MUCH. The future is unpredictable — I build a portfolio for all scenarios, not just one.

**A.5. Risk ≠ volatility**
Fatal risk (critical portfolio damage) is unacceptable. Operational loss (controlled trade loss) is acceptable as a working expense. I let winners grow, cut losses quickly if the thesis is violated.

**A.6. Execution discipline**
A correct but too-early entry ≈ wrong. 90% of control lies in risks and weeds (stops, limits, hedges). No restructuring based on news or emotions. Every action only via predefined triggers.

---

## SECTION B — TRADE ADMISSION FILTER (quick pre-screen)

The transaction is prohibited if at least one answer is NO. "Not quite YES" = NO.

| # | Question | Criterion |
|---|---|---|
| 1 | **I understand** | I can explain in 2 minutes: what I’m buying, revenue source, 3 main risks |
| 2 | **No coercion** | No margin, no forced-close scenarios |
| 3 | **Liquid** | I can close ≤ 3 trading days at ≤ 10% ADV |
| 4 | **I can withstand it** | −50% stress does not break me financially or psychologically |

Filter passed → proceed to 0-Gate and QPTA.

---

## 0‑GATE: ADMISSION TO DECISION (before any "what to do")

A decision may be discussed, but **executed** — only if:

- [ ] Investor Passport filled and is up to date (≤ 12 months)
- [ ] Portfolio Snapshot is current (≤ 7 days)
- [ ] Weekly Context is filled (≤ 7 days)
- [ ] Journal for last week is filled
- [ ] Company Card exists for the ticker (if Standard/Pro and this is a new position)

If not — action postponed, update inputs first.

---

## SECTION C — ASSET CLASSES (GREEN / YELLOW / ORANGE / RED)

### GREEN — ЯCore / Compounding
- Position limit: ≤ `[10]`% per asset (drift up to `[15]`% allowed due to growth; above — rebalance)
- Exception: broad ETF (SPY and analogs) — up to 100% within regime limits
- Risk management: not stop-loss, but fundamental/regime invalidation
- Entry rules: only BUY or STRONG BUY. In V_high — buying is prohibited.

**2 levels of protection instead of stop-loss:**

Level 1 — Fundamental stop (trigger-checklist mandatory):
```
✓ ROIC deterioration vs WACC for ___ consecutive quarters  [example: 3 quarters]
✓ Unit economics / margin breakdown
✓ Debt growth + FCF decrease simultaneously
✓ Moat degradation (competition / regulation)
✓ Toxic capital allocation (dilution, reckless M&A)
```

Level 2 — Technical Risk-Off (on SELL / STRONG SELL):
```
→ Stop adding
→ Reduce position to lower bound of target range
→ Partial conversion to cash/hedge until BUY returns
```

### YELLOW — Trades / Swing
- Position limit: ≤ `[5]`% per asset (drift up to `[7]`%)
- Risk per idea: 1R = `[1.0]`% capital (standard) / `[0.5]`% (Impulse BUY)
- Risk management: **stop-loss mandatory**
- No averaging down without predefined rule

### ORANGE — Asymmetry / Hedge / Tactics
- Hard limit: ≤ `[1]`% per position
- UsedRisk ≤ `[0.2]`% per idea
- Convexity mandatory: Profit/Loss ≥ 3:1
- Goal: asymmetry and tail-risk control, not "lottery"

### RED — Prohibited
0%. No trades: naked options, credit spreads, systematic premium selling, OTC, margin CFDs.

---

## SECTION D — PROHIBITED ACTIONS (ANTI‑RUIN)

Always prohibited (unless explicitly stated otherwise):
- Naked options
- Credit spreads (if prohibited)
- Systematic premium selling (short vol as strategy)
- Increasing risk during regime deterioration/drawdown
- "Impulse" trades without /blackbox and journal

---

## SECTION E — QPTA GATE

**QPTA = Quality / Price / Trend / Asymmetry**

| Gate | Question |
|---|---|
| **Q** (Quality) | Has the asset passed quality and risk filter? |
| **P** (Price) | Is the price in acceptable zone? (GREEN ≠ V_high) |
| **T** (Timing) | Does trend status allow entry? |
| **A** (Asymmetry) | Convexity ≥ 3:1? Hedge reduces portfolio risk? |

Rule: **all four must be YES**. One NO → trade **not allowed**.

*Example (educational case):*
```
Ticker: MSFT | Class: GREEN
Q: ROIC 30%+, stable FCF, wide moat → YES
P: Forward P/E at 5-year norm level, V_fair zone → YES
T: Trend Score = 7, Price > EMA200 → STRONG BUY → YES
A: GREEN doesn’t require 3:1, but price has margin of safety → YES
→ DECISION: EXECUTE
```

---

## SECTION E‑B — QUALITY GATES (extended quality control)

Each entry candidate passes 5 gates. FAIL on any mandatory → STOP.

| Gate | Check | PASS/FAIL | Mandatory? |
|---|---|---|---|
| **G0: Data** | Passport, portfolio, context current (≤7 days). Journal filled. Decision limit not exhausted. No trigger-state | ☐ | YES |
| **G1: Quality (Q)** | Company Card filled. NSM defined. No red flags (value trap, NOA, ESCORE) | ☐ | YES |
| **G2: Price (P)** | Valuation done. Fair Value Bear/Base/Bull. "What’s in the price" described. Upside ≥ threshold. False Precision Check passed | ☐ | YES |
| **G3: Timing (T)** | Macro-regime does not forbid. Trend not contradictory. No earnings <2 weeks. Not in first 24h after major news | ☐ | YES |
| **G4: Asymmetry (A)** | EV > 0. Upside/Downside ≥ 2:1. Size within limits (Heat, sector, FX, NBE). Alerts configured | ☐ | YES |

Detailed checklist — in `12_quality_gates.md`.

---

## РSECTION F — POSITION SIZE CALCULATION

### YELLOW (stocks/ETFs with stop)
```
Stop% = distance to stop in %
Position% = min(Class limit%, R / Stop%)
UsedRisk% = Position% × Stop%
Admission condition: UsedRisk% ≤ R
```

*Example: AAPL, YELLOW, R=1%, Stop%=5%*
*Position% = min(5%, 1%/5%) = min(5%, 20%) = 5%*
*UsedRisk% = 5% × 5% = 0.25% ✓ (≤ 1%)*

### ORANGE (options, premium risk)
```
UsedRisk% = paid premium% (or net debit%)
Condition: UsedRisk% ≤ 0.2%
```

*Example: Long Call SPY, premium = $150 with $50k portfolio = 0.30% → REJECT (> 0.2%)*
*Reduce: 1 contract with $75k portfolio = 0.20% → ОК*

### GREEN (core)
```
Pilot: ___% (example  3–5%)
Target: ___% (example  8–10%) upon scenario confirmation
Risk managed via fundamental triggers and portfolio limits
```

---

## SECTION G — PYRAMIDING AND ADDING

- Start with pilot when uncertain — market must pay for risk
- Pilot hits −1R → close (thesis/timing not confirmed)
- Pilot in loss, thesis alive, filters intact → hold, but **do not increase**

**YELLOW/ORANGE adding rule:**
Only at price above entry OR at breakout of confirming level (HH 30d / EMA50 / EMA200).

**GREEN adding rule:**
In V_low zone, if Q unchanged, regime allows exposure, Trend permits.
**Forbidden** to average if FCF/margin deteriorates or debt rises.

---

## SECTION H — TIMING: TREND SCORE

### Algorithm (EMA 10/20/50/90/200, ATR(14))

**Squeeze:** |EMA10 − EMA200| < 1.2 × ATR → status HOLD, no new buys.

**Scoring:** for each EMA: +1 if Price > EMA, −1 if below. +1 if slope up, −1 down. Sum = Trend Score.

| Score | Status | Allowed actions |
|---|---|---|
| ≥ 6 and Price > EMA200 | STRONG BUY | Full throttle within limits |
| ≥ 4 | BUY | Cautious entry |
| < 4 or Squeeze | HOLD | Hold only, no buying |
| ≤ −4 | SELL / STRONG SELL | Defense, reduce risk |

### Impulse BUY (YELLOW only)
All 6 conditions simultaneously: Trend Score ≥ 6 / Price > EMA50 / Slope EMA50 > 0 / No squeeze / Market ≠ Bear / Filter B passed.
Size: R_impulse = 0.5%.

---

## SECTION I — PORTFOLIO LIMITS (Heat / NBE / concentrations)

### I.1. Dual Heat budget

**Directional Heat** (risk of directional ideas):

| Market regime | Standard | Temporary increase |
|---|---|---|
| Bull | ≤ `[6]`% | ≤ `[10]`% |
| Neutral | ≤ `[4]`% | ≤ `[7]`% |
| Bear | ≤ `[3]`% | ≤ `[5]`% |

**Hedge Heat** (cost/risk of protection):

| Market regime | Limit |
|---|---|
| Bull | ≤ `[0.5]`% |
| Neutral | ≤ `[1.0]`% |
| Bear | ≤ `[2.0]`% |

### I.2. Net Beta Exposure (NBE)

| Regime | Market Cap | Macro Cap |
|---|---|---|
| Bull / Growth | ≤ `[1.00]` | ≤ `[1.00]` |
| Neutral | ≤ `[0.80]` | ≤ `[0.80]` |
| Bear / Downturn | ≤ `[0.50]` | ≤ `[0.50]` |

Effective ceiling = min(Market cap, Macro cap). **Macro has priority.**

### I.3. Concentrations

| Measurement | Limit |
|---|---|
| One ticker | ≤ `[10]`% (GREEN); ≤ `[5]`% (YELLOW) |
| Sector | ≤ `[30]`% |
| Country/jurisdiction (non-US) | ≤ `[10]`% |
| Currency (non-USD) | ≤ `[30]`% |
| Theme | ≤ `[10]`% |
| Theme Heat | ≤ `[35]`% of Directional Heat |

---

## SECTION J — PAUSE AND IMPULSE BAN

If the user is emotional or wants to act "urgently":
- Run `/blackbox`
- Pause rule: **minimum 2 minutes**, for YELLOW/ORANGE — **24 hours**, unless emergency due to limits.

---

## SECTION K — MANDATORY JOURNAL (HARD GATE)

Any action = journal entry:
- before execution: trade card (plan, stop/invalidation, QPTA)
- after execution: execution fact (price, size, deviation reasons)

**If no entry — action is considered as "not system-approved".** Trade without entry = Constitution violation.

---

## SECTION L — IDEA PROTOCOL (idea limit and triage)

```
Raw ideas per day: ≤ 3
Into analysis per week: ≤ 2
Into capital per month: ≤ 1
Active candidates (Research+Ready): ≤ 5
Ideas in Inbox: ≤ 10
Deep work simultaneously: 1
```

Assistant does NOT generate ideas proactively.

---

## SECTION M — DECISION FREQUENCY LIMIT (anti‑overtrading)

| Action | Limit/week |
|---|---|
| New entry (new ticker) | max 1 |
| Add to existing position | max 1 |
| Speculative trades (ORANGE) | max 1 |
| Into capital (real money entry) | max 1/month |

2+ impulsive decisions per week → forced Lite.

---

## SECTION N — MODE CHECKLIST (Lite / Standard / Pro)

### Lite
- [ ] Triage (noise/signal)
- [ ] Red line check
- [ ] No "executes" — only observe/alerts

### Standard
- [ ] QPTA + Quality Gates (G0, G2, G4 minimum)
- [ ] Portfolio limits (NBE/Heat/concentrations)
- [ ] Action plan (branch)
- [ ] Journal entry (if action)

### Pro
- [ ] Company Card updated (+ Fair Value + «What’s in the price» + False Precision)
- [ ] Context Card is up to date
- [ ] Scenario Map filled (+ ALERTS)
- [ ] Quality Gates G0–G4 complete
- [ ] /redteam + /audit
- [ ] Final report (archive)

**Auto-switches:** ROH < 6 → Lite (until ROH ≥ 8). ROH < 6 for two weeks → Lite + discussion. 2+ impulsive decisions → Lite for a week.

---

## SECTION O — DRAWDOWN AUTOPILOT

| Drawdown from peak | Actions |
|---|---|
| **−10%** | No changes, rule monitoring only |
| **−20%** | Pause new YELLOW/ORANGE. Reduce Directional Heat by 30–50%. Correlation audit |
| **−25%** | Audit "persistent losses". Forced exposure reduction. Ban scaling “by idea” |
| **Red button** | Survival threat → reduce risk / move to cash. Post-analysis after |

Rule: **in bad regime we cut risks, not “revenge trade.”**.

---

## APPENDIX — TRADE CARD (template)

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Ticker: ________  Date: ____  Price: ________

Context:
  Macro:      Growth / Downturn / Neutral
  Market:     Bull / Neutral / Bear
  Trend:      STRONG BUY / BUY / HOLD / SELL
  Valuation:  V_low / V_fair / V_high
  Uncertainty: Yes / No

Class: GREEN / YELLOW / ORANGE

Thesis (3 lines):
  Q: why quality / acceptable?
  P: why price acceptable? (zone + levels)
  T: what's the trigger / entry confirmation?

Risk math:
  R:           ___% (1.0% YELLOW / 0.5% Impulse / 0.2% ORANGE)
  Stop%:       ___%
  Class limit: ___% (10% / 5% / 1%)
  Position%  = min(Limit%, R/Stop%) = ___%
  UsedRisk%  = Position% × Stop% = ___%
  Directional Heat after: ___% (limit ___%)
  Hedge Heat after:       ___% (limit ___%)
  NBE after:              ___ (limit ___)
  Concentrations/themes: OK / NO
  Single point of failure: OK / NO

For GREEN (mandatory):
  Fundamental stop triggers: ___
  Technical Risk-Off plan on SELL/STRONG SELL: ___

Plan:
  Enrty:           ________
  Stop / max loss: ________
  Target (for Y/O): ________
  Invalidation conditions: ________

QPTA: Q[ ] P[ ] T[ ] A[ ] → DECISION: EXECUTE / CANCEL
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## APPENDIX — EXCEPTION PROTOCOL

**Violation** — deviation for "returns / opinion / emotion".
**Authorized deviation** — external constraint / force majeure; goal = risk control and reduction, NOT profit.

Allowed exceptions (closed list):
- Infrastructure/access (broker, exchange)
- Regulation/sanctions
- Corporate forced events
- Red button (survival threat)

NOT valid reasons: "I think…", news/tweets, "don’t want to realize loss", "need to recoup my losses".

**Master-rule:** an exception CANNOT increase tail risk.

---

*Version 3.1 · ROH threshold synchronized: Lite at < 6, exit at ≥ 8.*
