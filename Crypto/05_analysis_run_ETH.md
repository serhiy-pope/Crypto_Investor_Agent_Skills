# Analysis Run: ETH (Ethereum)
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
I want to consider ETH for the portfolio. What do you think?
```
---

**🤖 Agent (Standard):**

1) Checking documents: Passport / Constitution / Snapshot / Context — all current.
2) Checking idea limit (Idea Inbox) — slot available, 2/5 candidates.
3) Running `/idea_triage`:
   - Liquidity: ETH avg daily volume >$10B → ✓
   - Market cap: ~$300–400B → ✓
   - On taboo list? No → ✓
   - Status: **PIPELINE** (proceeding to analysis)

**Preliminary check against investor passport:**

I see the following constraints relevant to ETH:
- GREEN class candidate — requires 4+ year track record ✓ (ETH launched 2015)
- Smart contract audit — Ethereum is the most audited network in existence ✓
- Custody plan required — ETH can be self-custodied on hardware wallet ✓

This is not a ban — limits need to be verified after calculating size.

**Before going further — clarify:**
Are we considering ETH as GREEN (long-term core accumulation) or YELLOW (tactical cycle trade)?

---

## STEP 1 — CLASS CLARIFICATION

---
**👤 User:**
```
GREEN. I want to accumulate long-term.
```
---

**🤖 Agent:**

Understood. Launching full analysis for GREEN.

---

### BLOCK Q — QUALITY

**Network overview and value source:**
Ethereum is the leading smart contract platform. It hosts the majority of DeFi TVL (~$50–60B), the largest stablecoin settlement layer, and is the primary platform for NFTs, tokenized assets, and L2 ecosystem. ETH derives value from: (1) gas fee burn (EIP-1559), (2) staking yield (~4% APY), (3) L2 settlement demand, (4) collateral in DeFi.

**Key on-chain metrics (illustrative, verify current values):**

| Metric | Value | Assessment |
|---|---|---|
| Total Value Locked (DeFi) | ~$50–60B | ✓ Market-leading |
| Staking rate | ~28% of supply staked | ✓ High commitment |
| ETH burn rate (annualized) | ~500k–1M ETH/year | ✓ Deflationary regime |
| Developer activity | #1 by GitHub commits | ✓ |
| L2 ecosystem TVL | ~$15–20B | ✓ Growing adoption |

**Tokenomics:**
Post-Merge (Sep 2022): ETH is deflationary at current activity levels. No VC cliff unlocks. No premine concentration issues at current supply. Staking provides native yield and aligns holders.

**Network risks:**
1. L2 fee cannibalization — activity migrates to L2s, ETH base layer fees decrease
2. Competition from Solana, TON, other L1s capturing developer share
3. Regulatory risk — SEC classification as security (ongoing uncertainty)
4. Technical risk — upgrade failures (Dencun, further upgrades)

**Conclusion on Q:** YES ✓ — leading smart contract platform, deflationary tokenomics, massive DeFi moat, high staking commitment.

---

### BLOCK P — PRICE

**Valuation approach (crypto-specific):**

| Metric | Value | Assessment |
|---|---|---|
| NVT Ratio (Network Value / Transactions) | ~40–60x | Mid-cycle fair |
| P/TVL (Market Cap / DeFi TVL) | ~6–8x | Historical range 5–15x |
| P/Fees (Market Cap / Annualized Fees) | ~20–30x | Acceptable for dominant L1 |
| ETH/BTC ratio | ~0.04–0.06 | Historical range 0.03–0.08 |
| Cycle position | ~12 months post-halving | Mid-bull historically |

**Fair Value (Bear / Base / Bull) — 12-month horizon:**

| Scenario | Fair Value | Upside/Downside |
|---|---|---|
| Bear | $1,800 | −40% |
| Base | $4,000 | +25% |
| Bull | $7,000 | +120% |

**What's already in the price:** market is pricing in continued L2 adoption and moderate fee burn. Bull scenario requires institutional ETF inflows + DeFi activity acceleration.

**Conclusion on P:** YES ✓ — mid-cycle, not at ATH zone, P/TVL within historical range.

---

### BLOCK T — TIMING

```
BTC cycle position: Mid-bull (approx. 12–18 months post-halving)
Trend Score (daily ETH/USD): ≈ 6–7 → BUY / STRONG BUY
Price vs EMA200: Above → BULL
No squeeze: confirmed
Funding rates: Neutral (not euphoric)
```

Market = Bull ✓

**Conclusion on T:** YES ✓ — mid-bull cycle, trend aligned, entry allowed.

---

### BLOCK A — ASYMMETRY

For GREEN, 3:1 asymmetry is not required as strictly. Checking:
- Buying deflationary asset with native yield (staking) in mid-cycle
- Downside anchored by DeFi TVL demand and BTC correlation floor
- Upside: ETF flows, L2 adoption, tokenized assets growth

**EV check:**
EV = $7,000×30% + $4,000×50% + $1,800×20% = $2,100 + $2,000 + $360 = $4,460 (+39%)

**Conclusion on A:** YES ✓ — positive EV, mid-cycle entry, not euphoric.

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
GREEN limit: ≤ 15% per name (drift to 20%)
Current portfolio: $100,000
Recommend: pilot 5–7%, target 12–15% on confirmation
```

**Portfolio limit check after entry:**

```
Token concentration:
  ETH 6% → 6% < 15% → ✓ OK

Sector (L1/Smart Contract):
  Adding ETH 6% to existing BTC: ~6% + 40% BTC → correlated
  Monitor: total GREEN > 60% means no room for many YELLOW entries

Directional Heat:
  GREEN does not add to Directional Heat → Heat unchanged ✓

Single CEX exposure:
  Plan: hold 10% of ETH on CEX, 90% in cold storage
  CEX exposure contribution: 6% × 10% = 0.6% → well within 20% limit ✓

Custody plan:
  5,400 USDC → 5.4 ETH (at ~$1k price example)
  Cold wallet: 4.86 ETH (90%)
  CEX (staking/liquidity): 0.54 ETH (10%)
```

**All limits OK. Size confirmed.**

---

## STEP 3 — DEAL CARD

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
DEAL CARD
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Ticker: ETH     Date: 2026-03-06     Price: ~$3,200

Context:
  BTC Cycle:  Mid-bull (~12 months post-halving)
  Market:     Bull
  Trend:      BUY (Score ~6–7)
  Valuation:  Fair (P/TVL ~7x, within historical range)
  Uncertainty: Low-Medium

Class: GREEN

Thesis:
  Q: Dominant smart contract platform. Deflationary post-Merge.
     DeFi TVL $50B+, staking 28% of supply, L2 ecosystem leader.
  P: P/TVL ~7x — historical mid-range, not at peak.
     EV = +39% over 12 months at current scenario weights.
  T: Mid-bull cycle, trend BUY, funding rates neutral.

Math:
  Class: GREEN → no hard stop, management via fundamental triggers
  Position%:  6% (pilot) → target 14% on confirmation
  Amount:     $6,000

After entry:
  Directional Heat: unchanged ✓
  Stablecoin reserve: 12% → ✓ above 10% floor
  CEX concentration: +0.6% → total well within 20% ✓
  Token concentration: 6% < 15% ✓
  Single point of failure: NO ✓
  Custody: 90% cold storage, 10% CEX ✓

Fundamental stop triggers:
  1. ETH DeFi TVL falls below $20B for two consecutive months
  2. Net issuance turns positive (inflationary) for 3+ months
  3. Developer activity collapses — GitHub commits <50% of current
  4. Major protocol exploit draining >$1B in single event
  5. Regulatory prohibition as security in US + EU simultaneously

Technical Risk-Off plan on SELL/STRONG SELL:
  → Stop adding
  → Reduce from target 14% to pilot 6%
  → Wait for BUY return before restoring

Add-on rule (from 6% to 14%):
  → BTC confirms new ATH + ETH/BTC ratio improving, OR
  → Institutional ETF flows >$500M/week sustained

QPTA: Q[✓] P[✓] T[✓] A[✓]
Quality Gates: G0[✓] G1[✓] G2[✓] G3[✓] G4[✓]
→ DECISION: EXECUTE (pilot 6%)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## STEP 4 — ALERTS

Configure via `14_alerts_builder`:

| Type | Level/Event | Action |
|---|---|---|
| P1 (support) | $2,400 (bear zone / EMA200 test) | Review: is the cycle breaking? |
| P2 (add trigger) | ATH + 10% ($X) | Assess: Bull scenario triggered? |
| P3 (euphoria) | Funding rates > 0.1%/8h for 7 days | Trim 30%, do /redteam |
| F1 | DeFi TVL < $30B | Review thesis |
| F2 | Net issuance > 0 for 60 days | Tokenomics degraded |
| E1 | Major Ethereum upgrade | Update 06 + 08 |
| E2 | SEC ETH ruling | /triage_news — immediate |

---

## STEP 5 — SNAPSHOT UPDATE

After execution, update `04_portfolio_snapshot.md`:

**1. Add row to positions table:**
```
| ETH | GREEN | 6.0% | $3,200 | $3,200 | 0.0% | TVL/Issuance/Dev triggers | 0 | Cold/CEX | yes | OK |
```

**2. Update metrics:**
```
Cash/Stablecoins: 18% → 12%
ETH concentration: 0% → 6%
```

**3. Update pipeline:** ETH: Research → **Live**

**4. Journal entry (10):**
```
[2026-03-06] | ETH | Entry | $3,200 | 6% | GREEN | Q✓ P✓ T✓ A✓ | Calm
```

**Archive row:**
```
[2026-03-06] | ETH | Entry | GREEN | 6% | 0bp | +39% EV | Deflationary L1 + DeFi moat | TVL <$20B or inflation returns
```

---

## STEP 6 — ANTI‑HALLUCINATION: /audit

**AUDIT_NUMBERS block:**

| Category | Data |
|---|---|
| **Facts** | ETH Merge completed Sep 2022, staking ~28% supply, DeFi TVL ~$50-60B range |
| **Estimates/assumptions** | P/TVL ~7x, Trend Score ~6–7, Fair Value $1800/$4000/$7000 |
| **Source needed** | Exact current TVL (DeFiLlama), current burn rate (ultrasound.money), exact staking % |
| **What could be wrong** | Fair Value targets are wide; ETH/BTC ratio highly variable; cycle timing uncertain |

**Top 3 items for manual verification:**
1. Current DeFi TVL on DeFiLlama — exact figure
2. Current ETH issuance rate — ultrasound.money (inflationary or deflationary right now?)
3. ETH ETF flows — Bloomberg/CoinGlass for current institutional demand

---

## RUN SUMMARY

**What this run demonstrated:**

The system works sequentially: passport → constitution → snapshot → decision. The agent doesn't just analyze the asset — it checks it through all documents simultaneously and outputs a concrete action with numbers.

Key points:

**1.** Crypto analysis requires BTC cycle awareness as an additional timing filter — not just technical trend.

**2.** QPTA + Quality Gates — same framework as equities, but quality criteria (tokenomics, on-chain metrics, audits) replace financial statements.

**3.** Deal card includes custody plan — unlike equities, where custody is automatic.

**4.** Alerts include on-chain metrics (DeFi TVL, issuance rate) as fundamental triggers — no quarterly reports.

**5.** Anti-hallucination audit is critical — crypto metrics change daily; always verify current values.

---

*Version 1.0 · Full run: triage → QPTA + Gates → calculation → card → alerts → snapshot → journal → audit. ETH used as GREEN example (equivalent to ASML in equities system).*
