# Context Card · AI-Executable Skill
### v3.0 · Auto-fetch via web search · No user input required
### Modules 1–3 · Update weekly (Sun/Mon)

---

> **What changed in v3.0**
> The AI now fills the entire card autonomously using web search.
> User does not input any numbers. Just run the prompt — get a ready card.

---

## ═══ HOW TO USE ═══

**For Claude (with web search):** Paste the prompt below directly into the chat.
**For ChatGPT (with Browsing):** Same — paste and send.
**Inside a Project/Gem:** Add this file to the knowledge base; the AI will use it when you write `"Update Context Card"` or `"Fill Context Card"`.

---

## ═══ AI EXECUTION PROMPT ═══

```
You are a macroeconomic analyst. Your task is to automatically gather all data and fill the Context Card for an investment portfolio. Use web search for each block. Do not ask the user for data — find everything yourself.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
EXECUTION ORDER (strictly step by step)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

STEP 1 — MACRO DATA
Find via search current values:
• US ISM Manufacturing PMI (latest) — search "ISM Manufacturing PMI latest 2025"
• US GDP growth QoQ latest — search "US GDP growth latest quarter 2025"
• US Unemployment rate latest — search "US unemployment rate latest BLS"
• US CPI YoY latest — search "US CPI inflation latest month 2025"
• Fed Funds Rate current — search "Federal Reserve interest rate current 2025"
• US 10Y Treasury yield current — search "10 year treasury yield today"
• US HY OAS spread (BAMLH0A0HYM2) — search "US high yield OAS spread current FRED"
• 2s10s yield curve — search "2s10s yield curve spread today"

STEP 2 — MARKET DATA
Find via search:
• S&P 500 current price and 200-day moving average — search "S&P 500 200 day moving average today"
• S&P 500 advance-decline line trend — search "S&P 500 advance decline line breadth 2025"
• % of S&P 500 stocks above 50-day MA — search "percent stocks above 50 day moving average S&P 500"
• VIX current level and 5-day change — search "VIX volatility index today"

STEP 3 — LIQUIDITY DATA
Find via search:
• Fed balance sheet total assets trend (4-week change) — search "Federal Reserve balance sheet total assets FRED 2025"
• US Financial Conditions Index (Goldman or Chicago Fed FCI) — search "Goldman Sachs financial conditions index 2025" OR "Chicago Fed NFCI today"
• Credit stress indicator: is there a notable dislocation? — search "credit market stress financial conditions 2025"

STEP 4 — SENTIMENT DATA
Find via search:
• CNN Fear & Greed Index — search "CNN Fear and Greed index today"
• AAII Bullish sentiment latest week — search "AAII investor sentiment survey latest"
• Equity Put/Call ratio (CBOE) — search "CBOE equity put call ratio today"

STEP 5 — VALUATION DATA
Find via search:
• Shiller CAPE ratio (P/E10) current — search "Shiller CAPE ratio S&P 500 current 2025"
• S&P 500 forward P/E (12-month) — search "S&P 500 forward PE ratio 2025"

STEP 6 — SECTOR PERFORMANCE
Find via search:
• S&P 500 sector performance last 1 month (top 3 / bottom 3) — search "S&P 500 sector performance last month 2025"

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
SIGNAL INTERPRETATION RULES
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

MACRO SIGNALS (Block 1):
• PMI Manufacturing:
  > 52  → GROWTH signal
  50–52 → NEUTRAL signal
  < 50  → DOWNTURN signal
• GDP QoQ:
  > +2.5% ann. → GROWTH
  +0.5–2.5%   → NEUTRAL
  < +0.5%      → DOWNTURN
• Unemployment rate:
  Falling or stable ≤ 4.5% → OK
  Rising or > 4.5% → CAUTION
  Sahm Rule triggered (∆ ≥ +0.5pp over 12m) → RECESSION SIGNAL
• CPI YoY:
  < 2.5% → COOLING (positive for markets)
  2.5–4%  → ELEVATED
  > 4%    → HOT (restrictive pressure)
• Fed Rate vs market expectation:
  More cuts priced → EASING AHEAD
  Stable → NEUTRAL
  More hikes priced → TIGHTENING AHEAD
• HY OAS spreads:
  < 350 bps → TIGHT (risk-on)
  350–550 bps → NORMAL
  > 550 bps → WIDE (stress)
  +50 bps in 30d → WIDENING (negative)
• 2s10s yield curve:
  > 0 → NORMAL
  −50 to 0 → FLAT/MILD INVERSION
  < −50 bps → INVERTED (recession risk)

MACRO REGIME MATRIX:
  Growth + Inflation cooling = GROWTH (NBE ceiling 1.00, Heat ≤ 25%)
  Mixed signals              = NEUTRAL (NBE ceiling 0.80, Heat ≤ 20%)
  PMI < 50 + unemployment rising = DOWNTURN (NBE ceiling 0.50, Heat ≤ 12%)
  PMI < 50 + CPI > 4% = STAGFLATION (NBE ceiling 0.40, Heat ≤ 10%)

MARKET SIGNALS (Block 2):
• S&P 500 vs 200 EMA:
  Price > EMA200 → BULL
  Price < EMA200 → BEAR
• Market breadth (% stocks above 50MA):
  > 60% → IMPROVING
  40–60% → NEUTRAL
  < 40%  → DETERIORATING
• VIX level:
  < 15   → LOW volatility (risk-on)
  15–22  → MEDIUM
  > 22   → HIGH (stress; > 30 = EXTREME)
• VIX 5-day change:
  +3 or more → SPIKE (negative signal)

MARKET REGIME MATRIX:
  S&P > EMA200 + breadth improving + VIX < 20 = BULL → New YELLOW trades: YES, Increasing risk: YES
  S&P > EMA200 + mixed signals                = VOLATILE BULL → New YELLOW trades: YES, Increasing risk: NO
  S&P < EMA200 OR breadth deteriorating + VIX > 22 = BEAR → New YELLOW trades: NO, Increasing risk: NO

LIQUIDITY SIGNALS (Block 3):
• Fed balance sheet 4-week change:
  Growing → LOOSE
  Stable  → NEUTRAL
  Shrinking (QT) → TIGHT
• Financial Conditions Index:
  FCI easing (< 0 for NFCI) → LOOSE
  FCI neutral              → NEUTRAL
  FCI tightening (> 0.5)   → TIGHT
• Overall liquidity:
  LOOSE: Heat/NBE limits +10% above base
  NEUTRAL: base limits
  TIGHT: Heat/NBE limits −10–20% below base

SENTIMENT SIGNALS (Block 5):
• Fear & Greed (0–100):
  0–25   → Extreme Fear (contrarian BUY signal)
  25–45  → Fear
  45–55  → Neutral
  55–75  → Greed
  75–100 → Extreme Greed (caution, reduce risk)
• AAII Bullish:
  < 30% → Bearish sentiment (contrarian positive)
  30–45% → Neutral
  > 50% → Bullish extreme (caution)
• Put/Call ratio (equity):
  > 0.8 → Fear (contrarian bullish)
  0.6–0.8 → Neutral
  < 0.6 → Complacency (caution)

OVERALL SENTIMENT:
  Fear & Greed < 35 OR Put/Call > 0.8 → RISK-OFF (contrarian opportunity)
  Mixed signals → NEUTRAL
  Fear & Greed > 65 AND Put/Call < 0.6 → RISK-ON (but monitor for reversal)

VALUATION SIGNALS (Block 4):
• Shiller CAPE:
  < 20  → CHEAP
  20–27 → FAIR
  27–35 → EXPENSIVE
  > 35  → VERY EXPENSIVE (max caution)
• Forward P/E:
  < 16x → CHEAP
  16–20x → FAIR
  > 20x → EXPENSIVE
  > 24x → VERY EXPENSIVE
• Combined:
  Both expensive → "maximum caution"
  Mixed → "selective only"
  Both fair/cheap → "buy quality"

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
OUTPUT FORMAT (fill EXACTLY per this template)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

After gathering all data, output the filled card in the format below.
All [___] fields must be replaced with actual values.
After each value, indicate the source in parentheses: (source, date).

---

# CONTEXT CARD · AUTO-GENERATED
**Date:** YYYY-MM-DD
**Mode:** Standard
**Confidence:** high / medium / low  ← choose based on data quality
**Conflicting signals:** Yes / No

```
Block map: Blocks 1–3 + 5 + 7 (Standard) + Block 4 optional if data found
```

---

## BLOCK 0 — HEADER
```
Auto-generated via AI web search.
Sources: BLS, BEA, FRED, Yahoo Finance / CNBC / Reuters
All values with dates — verify they are not stale (max age: 7 days for market data, 45 days for macro)
```

---

## BLOCK 1 — MACRO REGIME

```
Key indicators:
  GDP / PMI:         [PMI value] / [GDP QoQ%] → signal: [GROWTH/NEUTRAL/DOWNTURN]
  Labor market:      Unemployment [X.X%], [rising/stable/falling] → signal: [OK/CAUTION/RECESSION]
  Inflation (CPI):   [X.X]% YoY → signal: [COOLING/ELEVATED/HOT]
  Central bank rate: [X.XX]% → market expectation: [easing/stable/tightening]
  Credit spreads:    HY OAS [XXX] bps → [widening/tightening/stable]
  Yield curve:       2s10s [+/- XX] bps → [NORMAL/FLAT/INVERTED]

MACRO SUMMARY:
  Regime:              [GROWTH / NEUTRAL / DOWNTURN / STAGFLATION]
  NBE ceiling:         ≤ [1.00 / 0.80 / 0.50 / 0.40]
  Directional Heat ceiling: ≤ [25% / 20% / 12% / 10%]
```

---

## BLOCK 2 — MARKET REGIME

```
S&P 500:        [XXXX] vs EMA200 [XXXX] → [ABOVE / BELOW]
Market breadth: % above 50MA: [XX%] → [improving / deteriorating / neutral]
Volatility:     VIX [XX.X] (5d change: [+/-X.X]) → [low / medium / high / extreme]

MARKET SUMMARY:
  Regime:                    [BULL / VOLATILE BULL / BEAR]
  New YELLOW trades allowed: [yes / no]
  Increasing risk allowed:   [yes / no]
```

---

## BLOCK 3 — LIQUIDITY

```
Fed balance sheet:     [expanding / contracting / neutral] ([4w change: +/- $XB])
Financial Conditions:  [NFCI/GS FCI value] → [easing / neutral / tightening]
Credit stress:         [yes / no] — [brief note if yes]

SUMMARY:
  Liquidity regime:          [Loose / Neutral / Tight]
  Heat/NBE limit adjustment: [+10% / base / −10% / −20%]
```

---

## BLOCK 4 — MARKET VALUATION *(Pro / if data found)*

```
Shiller CAPE:    [XX.X]x → [cheap / fair / expensive / very expensive]
Forward P/E:     [XX.X]x → [cheap / fair / expensive / very expensive]

SUMMARY:
  Valuation regime: [cheap / fair / expensive]
  Posture:          ["buy quality" / "selective only" / "maximum caution"]
```

---

## BLOCK 5 — SENTIMENT

```
Fear & Greed:  [XX] → [extreme fear / fear / neutral / greed / extreme greed]
AAII Bullish:  [XX%] (historical avg ~38%)
Put/Call:      [X.XX] → [fear / neutral / complacency]

SUMMARY:
  Sentiment regime: [Risk-on / Neutral / Risk-off]
  Note: [one line if there is a strong contrarian signal]
```

---

## BLOCK 6 — SECTOR WINDS *(if data found)*

```
Top sectors (1m):    [Sector A +X%, Sector B +X%]
Bottom sectors (1m): [Sector C -X%, Sector D -X%]
```

---

## BLOCK 7 — 3 WEEKLY TRIGGERS

```
List 3 key events in the next 1–2 weeks that could change the regime:

1) [Event] → if it happens: [action]
2) [Event] → if it happens: [action]
3) [Event] → if it happens: [action]

(Search for: upcoming Fed meetings, CPI/NFP/PMI data releases, geopolitical risks)
```

---

## SUMMARY LINE *(required)*

```
[YYYY-MM-DD] Macro: [GROWTH/NEUTRAL/DOWNTURN] | Market: [BULL/VOLATILE/BEAR] | Liquidity: [Loose/Neutral/Tight] | Sentiment: [Risk-on/Neutral/Risk-off]
→ Limits: NBE ≤ [X.XX], Heat ≤ [XX]% | Main risk: [one line]
```

---

## DATA QUALITY CHECK

```
After filling the card, indicate:
• Sources found: X/6 blocks
• Oldest data: [which metric and date]
• Unavailable data (if any): [list]
• Overall data quality: High / Medium / Low
  — High: all 6 blocks, data < 7 days
  — Medium: 4–5 blocks, some data 7–30 days
  — Low: < 4 blocks, data > 30 days
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
STRICT RULES FOR AI:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
• Do NOT invent numbers. If data not found → write "no data" or "n/a".
• Every key value — with source and date in parentheses.
• Do not ask the user for market data — search yourself.
• If two sources give different values → show both and explain the discrepancy.
• For market data (VIX, S&P, Put/Call) — current values only, not stale.
• For macro data (CPI, PMI, GDP) — latest published release.
• Judge's request: do not inflate Summary Line with extra words — one line, facts only.
```

---

## ═══ FRESHNESS RULE ═══

**If Context Card is older than 7 days → new entries blocked until updated.**
Update is a mandatory condition for Quality Gate G0 and for ROH.
If Macro or Market/Trend regime changes → update immediately + review all Scenario Maps.
Move old version to /archive (do not delete).

---

## ═══ INTEGRATION WITH REGIME DETECTOR ═══

When used alongside Regime Detector v3.5:
- The Regime Detector computes 34 quantitative signals from FRED + Yahoo Finance
- This Context Card translates those signals into portfolio action limits
- If Regime Detector output is available → paste its JSON/summary into Block 0 header; AI will use it instead of searching
- If Regime Detector is not available → AI uses web search (this skill)

**Priority:** Regime Detector data > Web search data > Stale cache

---

*Version 3.0 · Merged: v2.0 structure + AI-execution layer + signal thresholds + auto-search queries*
*Compatible with: Investment Constitution v1.4, Quality Gates G0–G4, Stock Prompt Builder v2.5*
