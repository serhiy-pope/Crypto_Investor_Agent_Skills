# 11_idea_triage.md — Crypto Idea Funnel v1.0

## PURPOSE

Structured process for processing new crypto investment ideas. Prevents "noise trading" and FOMO. Any new idea passes through the funnel BEFORE analysis begins.

**Key principle:** if an idea didn't make it to PIPELINE — it doesn't exist.

## WHEN TO USE

- User says: "What do you think about [token]?", "Saw an interesting protocol", "I was recommended…", "This narrative is exploding"
- User enters command `IDEA_TRIAGE`
- Assistant does NOT generate ideas on its own — only processes incoming ones from the user

---

## LIMITS (three-tier)

| Level | Limit | Meaning |
|---|---|---|
| Raw ideas (to register) | ≤ 3 per day | Just record without analysis |
| To analysis (Research status) | ≤ 2 per week | Full processing |
| To capital (actual entry) | ≤ 1 per month | Passed all Gates + QPTA |
| Candidates in progress (Research + Ready) | max 5 | Rest = Backlog |

---

## IDEA_TRIAGE TEMPLATE (ready to fill)

```
# IDEA_TRIAGE — New idea processing

**Token/Protocol:** ______________________
**Category:** ☐ L1  ☐ L2  ☐ DeFi  ☐ NFT/Gaming  ☐ AI/Data  ☐ RWA  ☐ Meme  ☐ Other: ________
**Idea source:** ☐ own research  ☐ recommendation  ☐ news  ☐ screener  ☐ social media  ☐ other: ________
**Date:** ________
**First thought (1 line):** _______________________________________
```

### STAGE 1: LIMIT CHECK

```
Ideas processed this week:           __/2 (max)
Candidates in Research/Ready now:    __/5 (max)

☐ PASS → continue
☐ Limit exhausted → BACKLOG (no analysis). Whom to replace? __________
```

### STAGE 2: QUICK FILTER (2 minutes)

Filter parameters are taken from 02_investor_passport.

```
| Criterion | Result | PASS/FAIL |
|---|---|---|
| Liquidity: avg daily volume > $___M (from 02) | | |
| Market cap: > $___M (from 02) | | |
| Smart contract audit exists (for DeFi/protocols) | | |
| Not on prohibited list (02_passport: no unaudited, no leveraged) | | |
| Token category not prohibited (meme, OTC, leveraged) | | |
| Doesn't duplicate existing position/candidate in same sector | | |
| Has basic thesis (not just "it's pumping!") | | |
| No major unlock in next 30 days (>5% supply) | | |

☐ All PASS → Stage 3
☐ Any FAIL → reason: _______ → ☐ Rejected  ☐ Backlog
```

**Auto-reject flags:**
- Anonymous team + no audit + no track record → DISCARD immediately
- Upcoming unlock >10% of circulating supply in 30 days → PARK at minimum
- Category = meme (if prohibited in passport) → DISCARD

### STAGE 3: MINI-SCORING (5–10 minutes)

Quick assessment without full analysis:

```
| Question | Answer (1 line) | Score (0–5) |
|---|---|---|
| Do I understand the protocol/value proposition? | | /5 |
| At least a hint of Network Effect or Protocol Moat? | | /5 |
| Tokenomics looks reasonable (no red flags)? | | /5 |
| Matches my style/role (from 02)? | | /5 |
| Catalyst or narrative visible on the horizon? | | /5 |

Total: __/25
```

### STAGE 4: DECISION

```
☐ ≥ 15 → RESEARCH status (do 06 + 08)
☐ 10–14 → BACKLOG (interesting, but not priority)
☐ < 10 → REJECTED ("fails even quick check")
```

### STAGE 5: RESEARCH → READY → LIVE

If idea received **Research** status:
1. Fill 06_asset_card (including on-chain valuation + Fair Value + tokenomics + False Precision)
2. Fill 08_scenario_map (Bull/Base/Bear + EV + alerts)
3. Pass 12_quality_gates
4. Based on results → **Ready** (awaiting entry) or back to **Backlog**

If status **Ready** → awaiting:
- Entry point (price/on-chain condition reached)
- Trigger from scenario map
- Slot in portfolio (limits not exhausted)
- Custody plan confirmed

On entry → record in 10_journal, update 04_snapshot.

---

## 4 FINAL TRIAGE STATUSES

| Status | Meaning | Where recorded |
|---|---|---|
| **DISCARD** | Didn't pass filter, not interesting | nowhere (or note) |
| **PARK (Backlog)** | Interesting, but not now | 04_snapshot (pipeline) |
| **PIPELINE (Research)** | Active analysis | 04_snapshot + start 06/08 |
| **ACTION (Ready → Live)** | Entry allowed | 04 + 09 + 10 |

---

## `IDEA_TRIAGE` COMMAND OUTPUT

```
╔══════════════════════════════════════════╗
  IDEA TRIAGE: [TOKEN]
  Category: [L1/L2/DeFi/etc.]
  Date: [DATE]
  
  Stage 1 (limit):          ☐ PASS  ☐ → Backlog
  Stage 2 (quick filter):   ☐ PASS  ☐ FAIL → reason: ___
  Stage 3 (mini-scoring):   __/25
  
  Result: ☐ DISCARD  ☐ PARK  ☐ PIPELINE  ☐ ACTION
  Next step: ___________________________
╚══════════════════════════════════════════╝
```

---

## RULES

1. Assistant does NOT skip stages. Even if user says "I've already checked everything".
2. Assistant does NOT generate ideas on its own initiative.
3. If 3+ ideas per day — gentle reminder about limit + suggest prioritizing.
4. Backlog is reviewed once a month (or when a slot opens up).
5. Triage result is ALWAYS one of 4 statuses: DISCARD / PARK / PIPELINE / ACTION.
6. Meme/narrative plays require explicit SPECULATOR role declaration before analysis.
7. Any protocol requiring wallet connection for research must have risk noted.
