# 12_quality_gates.md — Quality Control (Quality Gates) v2

## PURPOSE

Unified quality control checklist before making an investment decision. "Bad trades" are filtered out automatically. Used as final check in 09_final_report and as a training tool.

## WHEN TO USE

- Before any new entry or substantial addition
- When filling 09_final_report (required block)
- As an exercise during training (homework for modules 2/3)

---

## GATE 0: DATA AND READINESS

| Check | Status |
|---|---|
| 02_investor_passport filled and current | ☐ PASS ☐ FAIL |
| 03_constitution: limits known, Heat/NBE calculated | ☐ PASS ☐ FAIL |
| 04_snapshot updated (< 7 days) | ☐ PASS ☐ FAIL |
| 07_context updated (< 7 days) | ☐ PASS ☐ FAIL |
| 10_journal: entry for last week exists | ☐ PASS ☐ FAIL |
| Weekly decision limit not exhausted | ☐ PASS ☐ FAIL |
| Not in a trigger-state (from 02) | ☐ PASS ☐ FAIL |

**G0 FAIL = STOP.** Update documents / wait, then return.

---

## GATE 1: BUSINESS QUALITY (Q)

| Check | Status |
|---|---|
| 06_company_card filled | ☐ PASS ☐ FAIL |
| North Star Metric defined | ☐ PASS ☐ FAIL |
| Moat: at least 1 type with rating ≥ 3/5 | ☐ PASS ☐ FAIL |
| Value Trap check: not a trap | ☐ PASS ☐ FAIL |
| ESCORE / NOA: no critical red flags | ☐ PASS ☐ FAIL |
| Earnings quality: cash flow supports profit | ☐ PASS ☐ FAIL |

**G1 FAIL = STOP** (or YELLOW with rationale + "EXCEPTION" record).

---

## GATE 2: PRICE AND VALUATION (P)

| Check | Status |
|---|---|
| Valuation performed (ROP / Forward Triangulation / DCF) | ☐ PASS ☐ FAIL |
| Fair Value Bear/Base/Bull calculated (in 06) | ☐ PASS ☐ FAIL |
| Upside to Base fair value ≥ ___% (threshold from 02) | ☐ PASS ☐ FAIL |
| "What's already in the price" — described | ☐ PASS ☐ FAIL |
| False Precision Check: < 2 parameters with low confidence | ☐ PASS ☐ FAIL |
| Price vs. historical multiples: not at extreme | ☐ PASS ☐ FAIL |

**G2 FAIL = STOP** (or YELLOW with small size).

---

## GATE 3: TIMING AND CONTEXT (T)

| Check | Status |
|---|---|
| Macro regime (07) does NOT prohibit entry of this class | ☐ PASS ☐ FAIL |
| Trend/Momentum does not contradict direction | ☐ PASS ☐ FAIL |
| Nearest earnings > 2 weeks (or consciously accept risk) | ☐ PASS ☐ FAIL |
| No state-trigger (from 02: FOMO, sleep deprivation, anger) | ☐ PASS ☐ FAIL |
| Not within 24h of significant news | ☐ PASS ☐ FAIL |
| Role defined: SAVER / INVESTOR / SPECULATOR | ☐ PASS ☐ FAIL |

**G3 FAIL = WAIT.** Timing not suitable. Thesis may be good — postpone.

---

## GATE 4: ASYMMETRY, SIZE AND PORTFOLIO (A)

| Check | Status |
|---|---|
| 08_scenario_map: EV > 0 | ☐ PASS ☐ FAIL |
| Upside/Downside ratio ≥ 2:1 (or threshold from 02) | ☐ PASS ☐ FAIL |
| Position size within class limit (03) | ☐ PASS ☐ FAIL |
| Heat budget: sufficient UsedRisk | ☐ PASS ☐ FAIL |
| Sector concentration: within limit | ☐ PASS ☐ FAIL |
| FX concentration: within limit | ☐ PASS ☐ FAIL |
| NBE: does not violate Net Beta Exposure | ☐ PASS ☐ FAIL |
| Alerts configured (min: stop + earnings) | ☐ PASS ☐ FAIL |

**G4 FAIL = REDUCE SIZE or STOP.**

---

## SUMMARY TABLE

```
╔══════════════════════════════════════╗
  QUALITY GATES SUMMARY
  
  Ticker: ________     Date: ________
  Role: ☐ SAVER  ☐ INVESTOR  ☐ SPECULATOR
  
  G0 Data:        ☐ PASS  ☐ FAIL
  G1 Quality:     ☐ PASS  ☐ FAIL
  G2 Price:       ☐ PASS  ☐ FAIL
  G3 Timing:      ☐ PASS  ☐ FAIL
  G4 Asymmetry:   ☐ PASS  ☐ FAIL
  
  RESULT: ☐ ALL PASS → entry allowed
          ☐ FAIL → _____________________
          
  False precision: ☐ No  ☐ Yes → YELLOW only
╚══════════════════════════════════════╝
```

---

## APPLICATION MODES

| Mode | Required gates | Simplified |
|---|---|---|
| **Lite** | G0, G2, G4 | G1 (basic), G3 (no breadth/sentiment) |
| **Standard** | All 5 | — |
| **Pro** | All 5 + correlations with existing positions | — |

---

## RULES

1. Gates are passed SEQUENTIALLY. FAIL on G0 → G1–G4 not checked.
2. "Exception with rationale" — G1 and G2 only, MUST be recorded in journal.
3. Quality Gates are recorded in 09_final_report and 10_decision_journal.
4. If Gates not passed but entry made → "impulsive trade" → counts in ROH and Protocol Compliance.
