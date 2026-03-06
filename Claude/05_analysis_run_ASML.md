# Analysis Run: ASML
### Modules 1–3 · Format: user → agent dialogue · Training benchmark

---

> **How to read this document**
> Gray block — user request.
> White block — agent response.
> Arrows `→` show the agent's reasoning logic.
> This run demonstrates how all system documents work together.

---

## STEP 0 — IDEA TRIAGE (before analysis)

---
**👤 User:**
```
I want to consider ASML for the portfolio. What do you think?
```
---

**🤖 Agent (Standard):**

1) Checking documents: Passport / Constitution / Snapshot / Context — all current.
2) Checking idea limit (Idea Inbox) — slot available, 3/5 candidates.
3) Running `/idea_triage`:
   - Liquidity: ASML avg daily volume >$1B → ✓
   - Market cap: ~$290B → ✓
   - On taboo list? No → ✓
   - Status: **PIPELINE** (proceeding to analysis)

**Preliminary check against investor passport:**

I see the following constraints relevant to ASML:
- Country limit (non-US): ≤ 10% of portfolio → ASML trades on Nasdaq, but headquarters is incorporated in the Netherlands. Exposure counts as European jurisdiction.
- Currency: ASML reports in EUR, revenue partly in EUR → FX exposure exists, even when buying in USD.
- Current portfolio: 100% US, 100% USD → adding ASML would create the first international position.

This is not a ban — but limits need to be verified after calculating size.

**Before going further — clarify:**
Are we considering ASML as GREEN (long-term core) or YELLOW (tactical idea)?

---

## STEP 1 — CLASS CLARIFICATION

---
**👤 User:**
```
GREEN. I want to hold long-term.
```
---

**🤖 Agent:**

Understood. Launching full analysis for GREEN.

---

### BLOCK Q — QUALITY

**Business model and revenue source:**
ASML is the world's only manufacturer of EUV lithography systems (extreme ultraviolet lithography). Without their equipment it is impossible to produce chips at 7nm and below. Clients: TSMC, Samsung, Intel — the largest foundries on the planet.

**Financial metrics (based on public data):**

| Metric | Value | Assessment |
|---|---|---|
| ROIC | ~25–30% | ✓ High |
| Gross Margin | ~50–51% | ✓ Stable |
| FCF generation | Positive, growing | ✓ |
| Net Debt | Negative (cash > debt) | ✓ |
| Backlog | €36–40B (2–3 years of revenue) | ✓ Visibility high |

**Moat:**
EUV monopoly — structural, not temporary. The only supplier of critical technology for the entire semiconductor industry. Switching is impossible by definition — there is no alternative.

**Risks:**
1. Export restrictions (US/EU on shipments to China) — already partly implemented, China was ~15% of revenue
2. Semiconductor market cyclicality — foundry capex is volatile
3. Client concentration: TSMC ~40% of revenue

**Conclusion on Q:** YES ✓ — monopoly-quality business, high ROIC, strong balance sheet, clear revenue source.

---

### BLOCK P — PRICE

| Multiple | Value | Historical norm | Zone |
|---|---|---|---|
| Forward P/E | ~28–32x | 25–35x | V_fair |
| EV/EBITDA | ~20–22x | 18–25x | V_fair |
| P/FCF | ~30x | 25–35x | V_fair |

Price is in **V_fair** zone — not cheap, but not overheated. GREEN purchase in V_fair is allowed with BUY/STRONG BUY trend.

**Fair Value (Bear / Base / Bull):**

| Scenario | Fair Value | Upside/Downside |
|---|---|---|
| Bear | $520 | −28% |
| Base | $820 | +14% |
| Bull | $950 | +32% |

**What's already in the price:** the market is pricing in revenue growth of ~10–12% and stable margin. For Bull scenario, backlog acceleration + TSMC capex is needed.

**Conclusion on P:** YES ✓ — V_fair zone, GREEN purchase allowed.

---

### BLOCK T — TIMING

```
EMA10 > EMA20 > EMA50 > EMA90 > EMA200: Price above all → +5
Slopes: EMA10↑ EMA20↑ EMA50↑ EMA90→ EMA200↑ → +4
Total: Score ≈ 7–8 → STRONG BUY
Squeeze: |EMA10 − EMA200| >> 1.2×ATR → no squeeze
```

Market = Bull (SPY: Score 7, Price > EMA200) ✓

**Conclusion on T:** YES ✓ — STRONG BUY, entry allowed.

---

### BLOCK A — ASYMMETRY (for GREEN)

For GREEN, 3:1 asymmetry is not required as for options. Checking margin of safety:
- Buying quality business in V_fair, not V_high
- Downside limited by fundamentals (monopoly, FCF, backlog)
- Upside: revenue growth 15–20% per year per company guidance

**False Precision Check:**
Revenue growth, margin — medium confidence (good track record). Multiple — medium (cyclical industry). → acceptable for GREEN.

**Conclusion on A:** YES ✓ — price with reasonable margin of safety, not overpaying.

---

### QPTA + QUALITY GATES SUMMARY

| Gate | Result |
|---|---|
| Q (Quality) | ✓ YES |
| P (Price) | ✓ YES |
| T (Timing) | ✓ YES |
| A (Asymmetry) | ✓ YES |

Quality Gates: G0 ✓ G1 ✓ G2 ✓ G3 ✓ G4 ✓ → **ALL PASS**

**→ QPTA PASSED. Proceeding to size calculation.**

---

## STEP 2 — SIZE CALCULATION

---
**👤 User:**
```
Okay, QPTA passed. How much to buy?
```
---

**🤖 Agent:**

For GREEN, size is determined by class limit, not R/Stop% formula (no hard stop).

```
GREEN limit: ≤ 10% per name (drift to 15%)
Current portfolio: $100,000
Recommend: pilot 4–5%, target 8–10% on confirmation
```

**Portfolio limit check after entry:**

```
Country (Netherlands / EU):
  ASML 5% → 5% < 10% → ✓ OK

FX (EUR exposure):
  Indirect: ~5% × 35% = ~1.75% of portfolio
  FX limit ≤ 30% → ✓ OK (far from limit)

Sector (Technology / Semiconductors):
  Current tech (with SPY look-through): ~18%
  Adding ASML 5%: ~23% → ✓ below 30% limit

Directional Heat:
  GREEN does not add to Directional Heat → Heat unchanged ✓

NBE:
  ASML beta ~1.3
  Adding: 5% × 1.3 = 0.065 to NBE
  Current NBE: ~0.68, after: ~0.745 → ✓ below 1.00 limit
```

**All limits OK. Size confirmed.**

---

## STEP 3 — DEAL CARD

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
DEAL CARD
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Ticker: ASML     Date: 2025-02-16     Price: ~$720

Context:
  Macro:      Growth
  Market:     Bull
  Trend:      STRONG BUY (Score ~7–8)
  Valuation:  V_fair
  Uncertainty: None

Class: GREEN

Thesis:
  Q: Only manufacturer of EUV lithography systems.
     ROIC ~25–30%, FCF positive and growing,
     backlog €36–40B, no debts.
  P: Forward P/E ~30x — within historical norm,
     V_fair zone, purchase allowed.
  T: Trend Score ~7–8 → STRONG BUY, Price > EMA200,
     no squeeze.

Math:
  Class: GREEN → no hard stop, management
         via fundamental triggers
  Position%:  5% (pilot) → target 10% on confirmation
  Amount:     $5,000

After entry:
  Directional Heat: 1.39% (unchanged) ✓
  Hedge Heat:       0.21% (unchanged) ✓
  NBE:              ~0.745 (limit 1.00) ✓
  Tech sector:      ~23% (limit 30%) ✓
  Country EU:        5% (limit 10%) ✓
  Single point of failure: NO ✓

Fundamental stop triggers:
  1. ROIC falls below 18% for two consecutive quarters
  2. Gross margin drops below 45% — pricing pressure
  3. Backlog shrinks by more than 30% y/y
  4. Export restrictions close >30% of revenue
  5. Appearance of a real EUV competitor

Technical Risk-Off plan on SELL/STRONG SELL:
  → Stop adding
  → Reduce position from 10% to 5%
  → Wait for BUY return before restoring

Add-on rule (from 5% to 10%):
  → Price above $720 on next purchase, OR
  → Confirmation: quarterly report without negative surprises

QPTA: Q[✓] P[✓] T[✓] A[✓]
Quality Gates: G0[✓] G1[✓] G2[✓] G3[✓] G4[✓]
→ DECISION: EXECUTE (pilot 5%)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## STEP 4 — ALERTS

Configure via `14_alerts_builder`:

| Type | Level/Event | Action |
|---|---|---|
| P1 (stop) | N/A (GREEN, fundamental stop) | — |
| P2 (support) | $640 (EMA200 zone) | Review: add or wait? |
| P3 (resistance) | $850 (Bull zone) | Assess: Bull scenario triggered? |
| F1 | Backlog < €32B | Review thesis |
| F2 | Gross Margin < 48% | Check pricing pressure |
| E1 | Earnings (quarterly) | Update 06 + 08 |
| E2 | Export regulation | /triage_news |

---

## STEP 5 — SNAPSHOT UPDATE

After execution, update `04_portfolio_snapshot.md`:

**1. Add row to positions table:**
```
| ASML | GREEN | 5.0% | $720 | $720 | 0.0% | ROIC/Margin/Backlog triggers | 0 | yes | OK |
```

**2. Update metrics:**
```
Cash: 38.5% → 33.5%
NBE: ~0.68 → ~0.745
Tech sector: ~18% → ~23%
Country EU: 0% → 5%
```

**3. Update pipeline:** ASML: Research → **Live**

**4. Journal entry (10):**
```
[2025-02-16] | ASML | Entry | $720 | 5% | GREEN | Q✓ P✓ T✓ A✓ | Calm
```

**Archive row:**
```
[2025-02-16] | ASML | Entry | GREEN | 5% | 0bp | +11% | EUV monopoly + backlog | Loss of >30% backlog or margin <45%
```

---

## STEP 6 — ANTI‑HALLUCINATION: /audit

**AUDIT_NUMBERS block:**

| Category | Data |
|---|---|
| **Facts** | Revenue €28.3B (FY2024), Gross Margin ~51%, Backlog €36–40B, ROIC ~25–30% |
| **Estimates/assumptions** | Forward P/E ~30x, Beta ~1.3, target price $820/$950/$520 |
| **Source needed** | Exact backlog (earnings call), current export restrictions |
| **What could be wrong** | ROIC range is wide (25–30%), beta may be higher in Bear |

**Top 3 items for manual verification:**
1. Backlog — exact figure from latest ASML report
2. TSMC capex guidance for 2025 (demand confirmation)
3. Export restriction status (DUV for additional countries?)

---

## RUN SUMMARY

**What this run demonstrated:**

The system works sequentially: passport → constitution → snapshot → decision. The agent doesn't just analyze the asset — it checks it through all documents simultaneously and outputs a concrete action with numbers.

Key points:

**1.** The agent itself raised the currency and geography question — not because it's smart, but because the constitution specifies limits.

**2.** QPTA + Quality Gates — not a formality. If Trend were HOLD or price V_high — the trade would not pass, regardless of quality.

**3.** Deal card — not a report, but a contract with yourself. Stop triggers are written before entry.

**4.** Alerts are set up immediately — the position is not left "without follow-up".

**5.** After every trade the snapshot is updated. Without this, the system loses touch with reality.

---

*Version 3.0 · Full run: triage → QPTA + Gates → calculation → card → alerts → snapshot → journal → audit.*
