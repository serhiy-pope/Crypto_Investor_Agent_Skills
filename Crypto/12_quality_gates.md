# 12_quality_gates.md — Crypto Quality Control (Quality Gates) v1.0

## PURPOSE

Unified quality control checklist before making a crypto investment decision. "Bad trades" are filtered out automatically. Used as final check in 09_final_report and as a training tool.

## WHEN TO USE

- Before any new entry or substantial addition
- When filling 09_final_report (required block)
- After IDEA_TRIAGE reaches Research status
- Before moving a candidate from Ready to Live

---

## GATE 0: DATA AND READINESS

| Check | Status |
|---|---|
| 02_investor_passport filled and current | ☐ PASS ☐ FAIL |
| 03_constitution: limits known, Heat/custody calculated | ☐ PASS ☐ FAIL |
| 04_snapshot updated (< 7 days) | ☐ PASS ☐ FAIL |
| 07_context updated (< 7 days) | ☐ PASS ☐ FAIL |
| 10_journal: entry for last week exists | ☐ PASS ☐ FAIL |
| Weekly decision limit not exhausted | ☐ PASS ☐ FAIL |
| Not in a trigger-state (from 02) | ☐ PASS ☐ FAIL |
| BTC regime check: not in BEAR without explicit plan | ☐ PASS ☐ FAIL |

**G0 FAIL = STOP.** Update documents / wait, then return.

---

## GATE 1: ASSET QUALITY (Q)

| Check | Status |
|---|---|
| 06_asset_card filled | ☐ PASS ☐ FAIL |
| North Star Metric defined (TVL / active addresses / fees / issuance rate) | ☐ PASS ☐ FAIL |
| Network effect or protocol moat: at least 1 type rated ≥ 3/5 | ☐ PASS ☐ FAIL |
| Smart contract audit passed (for DeFi/protocols) | ☐ PASS ☐ FAIL |
| Tokenomics: no red flags (excessive inflation, VC cliff <90d, anonymous team) | ☐ PASS ☐ FAIL |
| Token utility is real (not pure speculation/meme without utility) | ☐ PASS ☐ FAIL |
| No major unlock in next 30 days (>5% circulating supply) | ☐ PASS ☐ FAIL |

**G1 FAIL = STOP** (or YELLOW with rationale + "EXCEPTION" record in journal).

---

## GATE 2: PRICE AND VALUATION (P)

| Check | Status |
|---|---|
| On-chain valuation performed (P/TVL / NVT / P/Fees) | ☐ PASS ☐ FAIL |
| Fair Value Bear/Base/Bull calculated (in 06) | ☐ PASS ☐ FAIL |
| Upside to Base fair value ≥ ___% (threshold from 02) | ☐ PASS ☐ FAIL |
| "What's already in the price" — described | ☐ PASS ☐ FAIL |
| False Precision Check: < 2 parameters with low confidence | ☐ PASS ☐ FAIL |
| Cycle position: not at historical euphoria zone (NUPL > 0.75 or Extreme Greed) | ☐ PASS ☐ FAIL |
| Price vs historical multiples: not at extreme end of range | ☐ PASS ☐ FAIL |

**G2 FAIL = STOP** (or YELLOW with small size).

---

## GATE 3: TIMING AND CONTEXT (T)

| Check | Status |
|---|---|
| BTC market regime (07) does NOT prohibit entry of this class | ☐ PASS ☐ FAIL |
| Trend/Momentum does not contradict direction | ☐ PASS ☐ FAIL |
| No major token unlock within 2 weeks (if YELLOW/ORANGE) | ☐ PASS ☐ FAIL |
| No state-trigger (from 02: FOMO, sleep deprivation, anger) | ☐ PASS ☐ FAIL |
| Not within 24h of major news/pump | ☐ PASS ☐ FAIL |
| Role defined: SAVER / INVESTOR / SPECULATOR | ☐ PASS ☐ FAIL |
| BTC dominance trend compatible with this asset class (alt season check) | ☐ PASS ☐ FAIL |

**G3 FAIL = WAIT.** Timing not suitable. Thesis may be good — postpone.

---

## GATE 4: ASYMMETRY, SIZE, PORTFOLIO AND CUSTODY (A)

| Check | Status |
|---|---|
| 08_scenario_map: EV > 0 | ☐ PASS ☐ FAIL |
| Upside/Downside ratio ≥ 3:1 (or threshold from 02) | ☐ PASS ☐ FAIL |
| Position size within class limit (03) | ☐ PASS ☐ FAIL |
| Heat budget: sufficient UsedRisk available | ☐ PASS ☐ FAIL |
| Sector/narrative concentration: within limit | ☐ PASS ☐ FAIL |
| Single CEX concentration: within limit (≤ 20% of portfolio) | ☐ PASS ☐ FAIL |
| Hot wallet exposure after entry: within limit (≤ 20%) | ☐ PASS ☐ FAIL |
| Custody plan defined and feasible before entry | ☐ PASS ☐ FAIL |
| Alerts configured (min: 1 price + 1 on-chain metric) | ☐ PASS ☐ FAIL |

**G4 FAIL = REDUCE SIZE or STOP.**

---

## SUMMARY TABLE

```
╔══════════════════════════════════════╗
  CRYPTO QUALITY GATES SUMMARY
  
  Token: ________     Date: ________
  Role: ☐ SAVER  ☐ INVESTOR  ☐ SPECULATOR
  BTC cycle: ________
  
  G0 Data:        ☐ PASS  ☐ FAIL
  G1 Quality:     ☐ PASS  ☐ FAIL
  G2 Price:       ☐ PASS  ☐ FAIL
  G3 Timing:      ☐ PASS  ☐ FAIL
  G4 Asymmetry:   ☐ PASS  ☐ FAIL
  
  RESULT: ☐ ALL PASS → entry allowed
          ☐ FAIL → _____________________
          
  False precision: ☐ No  ☐ Yes → YELLOW only
  Custody plan: ☐ Defined  ☐ Missing → STOP
╚══════════════════════════════════════╝
```

---

## APPLICATION MODES

| Mode | Required gates | Simplified |
|---|---|---|
| **Lite** | G0, G2, G4 | G1 (basic), G3 (no BTC dominance check) |
| **Standard** | All 5 | — |
| **Pro** | All 5 + correlations with existing positions + tokenomics health check | — |

---

## CRYPTO-SPECIFIC RULES

1. Gates are passed SEQUENTIALLY. FAIL on G0 → G1–G4 not checked.
2. "Exception with rationale" — G1 and G2 only, MUST be recorded in journal.
3. G1 FAIL on "no audit" → ORANGE class maximum (small speculative size), not GREEN/YELLOW core.
4. G3 FAIL during BEAR market → no exceptions for YELLOW/ORANGE entries.
5. G4 custody check is non-negotiable — no entry without custody plan.
6. Quality Gates are recorded in 09_final_report and 10_decision_journal.
7. If Gates not passed but entry made → "impulsive trade" → counts in ROH and Protocol Compliance.
