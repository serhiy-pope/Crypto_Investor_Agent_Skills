# Context Card — Crypto · AI-Executable Skill
### v1.0 · Auto-fetch via web search · No user input required
### Modules 1–3 · Update weekly (Sun/Mon)

---

> **What this card does**
> Provides the complete crypto market background context needed before any trade decision.
> The AI fills the card autonomously using web search.
> User does not input any numbers. Just run the prompt — get a ready card.

---

## ═══ HOW TO USE ═══

**For Claude (with web search):** Paste the prompt below directly into the chat.
**For ChatGPT (with Browsing):** Same — paste and send.
**Inside a Project/Gem:** Add this file to the knowledge base; the AI will use it when you write `"Update Context Card"` or `"Fill Crypto Context Card"`.

---

## ═══ AI EXECUTION PROMPT ═══

```
You are a crypto market analyst. Your task is to automatically gather all data and fill the
Crypto Context Card for a portfolio. Use web search for each block. Do not ask the user for
data — find everything yourself.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
EXECUTION ORDER (strictly step by step)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

STEP 1 — MACRO / GLOBAL RISK CONTEXT
Find via search current values:
• US Fed Funds Rate — search "Federal Reserve interest rate current 2026"
• US CPI YoY latest — search "US CPI inflation latest 2026"
• DXY (US Dollar Index) level and trend — search "DXY dollar index today 2026"
• US 10Y Treasury yield — search "10 year treasury yield today"
• Global risk-on/risk-off: S&P 500 trend — search "S&P 500 trend vs 200 day moving average 2026"

STEP 2 — BTC MARKET DATA
Find via search:
• BTC current price — search "Bitcoin price today 2026"
• BTC 200-day moving average — search "Bitcoin 200 day moving average today"
• BTC dominance % — search "Bitcoin dominance percentage today CoinMarketCap"
• BTC YTD return — search "Bitcoin price YTD return 2026"
• BTC halving cycle position — search "Bitcoin halving 2024 months since halving"

STEP 3 — CRYPTO MARKET STRUCTURE
Find via search:
• Total crypto market cap — search "total crypto market cap today 2026"
• Total DeFi TVL — search "total DeFi TVL DeFiLlama today 2026"
• Stablecoin market cap total — search "total stablecoin market cap 2026"
• ETH/BTC ratio — search "ETH BTC ratio today"
• Total crypto market cap ex-BTC (altcoin market cap) — search "altcoin market cap total 2026"

STEP 4 — ON-CHAIN AND DERIVATIVES SENTIMENT
Find via search:
• Crypto Fear & Greed Index — search "crypto fear greed index today alternative.me"
• BTC funding rates (perpetual futures) — search "Bitcoin perpetual futures funding rate today"
• BTC open interest — search "Bitcoin futures open interest today CoinGlass"
• BTC exchange netflows (7d) — search "Bitcoin exchange netflows 7 day Glassnode 2026"
• BTC long-term holder supply % — search "Bitcoin long term holder supply percent Glassnode 2026"
• NUPL (Net Unrealized Profit/Loss) — search "Bitcoin NUPL Glassnode today"

STEP 5 — LIQUIDITY AND CAPITAL FLOWS
Find via search:
• Stablecoin supply change (30d) — search "USDT USDC supply change 30 days 2026"
• BTC ETF net flows (7d) — search "Bitcoin spot ETF net flows weekly 2026"
• ETH ETF net flows (7d) — search "Ethereum spot ETF net flows 2026"

STEP 6 — SECTOR PERFORMANCE AND NARRATIVES
Find via search:
• Top performing crypto sectors/narratives (1 month) — search "best performing crypto sectors narratives last month 2026"
• Bottom performing sectors (1 month) — search "worst performing crypto sectors last month 2026"

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
SIGNAL INTERPRETATION RULES
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

MACRO SIGNALS (Block 1):
• DXY trend:
  Falling or < 100   → POSITIVE for crypto (risk-on, dollar weakening)
  Stable 100–103     → NEUTRAL
  Rising or > 103    → NEGATIVE (risk-off, dollar strengthening)
• Fed policy:
  Cutting rates      → POSITIVE (liquidity expanding)
  On hold            → NEUTRAL
  Hiking rates       → NEGATIVE (tightening, risk-off)
• CPI YoY:
  Falling < 3%       → COOLING (Fed more likely to cut → positive)
  3–4%               → ELEVATED (uncertainty)
  > 4%               → HOT (hawkish pressure)
• S&P 500 vs EMA200:
  Above → RISK-ON globally
  Below → RISK-OFF globally

BTC MARKET SIGNALS (Block 2):
• BTC vs 200 DMA:
  Price > 200 DMA    → BULL market
  Price < 200 DMA    → BEAR market
• BTC Dominance:
  Rising > 55%       → Bitcoin season (BTC outperforms, alts underperform)
  Falling < 50%      → Altcoin season (alts outperform BTC)
  45–55%             → NEUTRAL / transition
• BTC Cycle (months since April 2024 halving):
  0–6 months         → Pre/early bull — accumulation phase
  6–18 months        → Mid bull — main uptrend historically
  18–30 months       → Late bull / peak zone — caution, reduce risk
  30+ months         → Bear / accumulation — defensive posture

REGIME MATRIX (BTC + Macro):
  BTC > EMA200 + DXY falling + Fed cutting   = BULL RISK-ON → Full Green/Yellow allowed
  BTC > EMA200 + mixed macro                 = VOLATILE BULL → Green OK, Yellow cautious
  BTC < EMA200 OR DXY spiking               = BEAR / RISK-OFF → Green hold only, no Yellow

ON-CHAIN SENTIMENT SIGNALS (Block 4):
• Fear & Greed (0–100):
  0–25   → Extreme Fear (contrarian BUY signal for GREEN)
  25–40  → Fear
  40–60  → Neutral
  60–80  → Greed
  80–100 → Extreme Greed (reduce risk, do NOT enter new positions)
• Funding Rates (perpetual futures):
  Neutral (−0.01% to +0.02%/8h) → healthy, no extreme leverage
  Positive > 0.05%/8h            → overleveraged longs, correction risk
  Negative < −0.02%/8h           → overleveraged shorts, squeeze potential
• NUPL:
  < 0     → Capitulation (extreme buy zone for long-term)
  0–0.25  → Hope/Fear (accumulation)
  0.25–0.5 → Optimism/Belief (normal bull)
  0.5–0.75 → Greed (late bull, caution)
  > 0.75  → Euphoria (exit zone for YELLOW/ORANGE)
• Exchange Netflows (7d):
  Outflow (positive) → accumulation signal (coins leaving exchanges)
  Inflow (negative)  → selling pressure signal

LIQUIDITY SIGNALS (Block 5):
• Stablecoin supply growing  → new capital entering crypto → positive
• Stablecoin supply shrinking → capital exiting → negative
• ETF net inflows positive   → institutional demand → positive
• ETF net outflows           → institutional selling → negative

SECTOR/NARRATIVE SIGNALS (Block 6):
  Leaders last month → potential continuation or mean reversion play
  Laggards last month → potential rotation target or permanent decline

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
OUTPUT FORMAT (fill EXACTLY per this template)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

After gathering all data, output the filled card in the format below.
All [___] fields must be replaced with actual values.
After each value, indicate the source in parentheses: (source, date).

---

# CRYPTO CONTEXT CARD · AUTO-GENERATED
**Date:** YYYY-MM-DD
**Mode:** Standard
**Confidence:** high / medium / low
**Conflicting signals:** Yes / No

---

## BLOCK 0 — HEADER
```
Auto-generated via AI web search.
Sources: CoinMarketCap, DeFiLlama, Glassnode, CoinGlass, alternative.me, FRED, Reuters
All values with dates — verify market data is not stale (max age: 7 days)
```

---

## BLOCK 1 — MACRO / GLOBAL RISK

```
DXY:             [XXX.X] → trend: [rising/falling/stable] → [POSITIVE/NEUTRAL/NEGATIVE for crypto]
Fed policy:      [X.XX]% → [cutting/on hold/hiking] → [POSITIVE/NEUTRAL/NEGATIVE]
CPI YoY:         [X.X]% → [COOLING/ELEVATED/HOT]
US 10Y yield:    [X.XX]%
S&P 500:         vs EMA200 → [ABOVE/BELOW] → global risk: [ON/OFF]

MACRO SUMMARY:
  Global regime: [RISK-ON / NEUTRAL / RISK-OFF]
  Impact on crypto: [positive / neutral / negative headwind]
```

---

## BLOCK 2 — BTC MARKET REGIME

```
BTC price:       $[XXXXX] vs 200 DMA $[XXXXX] → [ABOVE/BELOW]
BTC dominance:   [XX]% → [rising/falling/stable] → [Bitcoin season / Altcoin season / Neutral]
BTC cycle:       [XX] months since April 2024 halving → [Early/Mid/Late Bull / Bear]
BTC YTD:         [+/-XX]%

BTC MARKET SUMMARY:
  Regime:                    [BULL / VOLATILE BULL / BEAR]
  BTC season or Alt season:  [Bitcoin / Altcoin / Neutral]
  New GREEN entries:         [yes / no]
  New YELLOW entries:        [yes / no]
  Increasing risk:           [yes / no]
```

---

## BLOCK 3 — CRYPTO MARKET STRUCTURE

```
Total crypto market cap:    $[X.X]T → [expanding/contracting]
Total DeFi TVL:             $[XX]B → trend: [growing/shrinking/stable]
Stablecoin market cap:      $[XXX]B → 30d change: [+/-XX]B
ETH/BTC ratio:              [0.0XX] → trend: [rising/falling/stable]

SUMMARY:
  Market structure:     [Healthy / Stretched / Contracting]
  Capital flow signal:  [Inflow / Neutral / Outflow]
```

---

## BLOCK 4 — ON-CHAIN AND DERIVATIVES SENTIMENT

```
Crypto Fear & Greed:  [XX]/100 → [extreme fear / fear / neutral / greed / extreme greed]
BTC Funding Rate:     [+/-X.XX]%/8h → [overleveraged longs / neutral / overleveraged shorts]
BTC Open Interest:    $[XX]B → [elevated/normal/low]
BTC Exchange Netflow: [+/-$XXM] (7d) → [accumulation/selling pressure]
LTH Supply:           [XX]% → [accumulating/distributing]
NUPL:                 [X.XX] → [capitulation / hope / optimism / greed / euphoria]

SUMMARY:
  Sentiment regime:   [Risk-on / Neutral / Risk-off]
  Leverage status:    [Healthy / Elevated / Extreme]
  Note: [one line if meaningful contrarian signal]
```

---

## BLOCK 5 — LIQUIDITY AND CAPITAL FLOWS

```
Stablecoin supply (30d change):  [+/-$XXB] → [capital entering / neutral / capital exiting]
BTC ETF net flows (7d):          [+/-$XXM] → [institutional buying / neutral / selling]
ETH ETF net flows (7d):          [+/-$XXM] → [institutional buying / neutral / selling]

SUMMARY:
  Liquidity regime:    [Expanding / Neutral / Contracting]
  Adjustment to Heat:  [+10% / base / −10%]
```

---

## BLOCK 6 — SECTOR WINDS

```
Top sectors/narratives (1m):    [Sector +X%, Sector +X%]
Bottom sectors/narratives (1m): [Sector -X%, Sector -X%]
Dominant narrative this week:   ___
```

---

## BLOCK 7 — 3 WEEKLY TRIGGERS

```
List 3 key events in the next 1–2 weeks that could change the regime:

1) [Event] → if it happens: [action]
2) [Event] → if it happens: [action]
3) [Event] → if it happens: [action]

(Search for: Fed meetings, CPI data, major protocol upgrades, ETF approval/rejection,
regulatory hearings, major token unlocks, BTC ETF options expiration)
```

---

## SUMMARY LINE *(required)*

```
[YYYY-MM-DD] Macro: [RISK-ON/NEUTRAL/RISK-OFF] | BTC: [BULL/VOLATILE/BEAR] | Sentiment: [Greedy/Neutral/Fearful] | Liquidity: [Expanding/Neutral/Contracting]
→ BTC cycle: [Early/Mid/Late Bull / Bear] | Season: [BTC/Alt/Neutral] | Heat ceiling: [base/+10%/-10%] | Main risk: [one line]
```

---

## DATA QUALITY CHECK

```
After filling the card, indicate:
• Blocks filled: X/7
• Oldest data: [which metric and date]
• Unavailable data (if any): [list]
• Overall data quality: High / Medium / Low
  — High: all 7 blocks, data < 7 days
  — Medium: 5–6 blocks, some data 7–30 days
  — Low: < 5 blocks, data > 30 days
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
STRICT RULES FOR AI:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
• Do NOT invent numbers. If data not found → write "no data" or "n/a".
• Every key value — with source and date in parentheses.
• Do not ask the user for market data — search yourself.
• If two sources give different values → show both and explain the discrepancy.
• For market/on-chain data — current values only, not stale.
• Summary Line: one line, facts only — no extra words.
```

---

## ═══ FRESHNESS RULE ═══

**If Context Card is older than 7 days → new entries blocked until updated.**
Update is a mandatory condition for Quality Gate G0 and for ROH.
If BTC regime changes (crosses 200 DMA) → update immediately + review all Scenario Maps.
Move old version to /archive (do not delete).

---

## ═══ REGIME DECISION TABLE ═══

| BTC Regime | Macro | Sentiment | Action |
|---|---|---|---|
| BULL (>EMA200) | Risk-ON | Fear/Neutral | Full throttle — GREEN accumulate, YELLOW enter |
| BULL (>EMA200) | Risk-ON | Extreme Greed | Caution — no new YELLOW, trim if euphoric |
| VOLATILE BULL | Mixed | Neutral | GREEN pilot only, YELLOW small stops |
| BEAR (<EMA200) | Risk-OFF | Any | GREEN hold only, NO new YELLOW/ORANGE |
| BEAR (<EMA200) | Risk-OFF | Extreme Fear | GREEN add pilot, no YELLOW |

---

*Version 1.0 · Crypto adaptation. Replaced: S&P macro → BTC cycle + on-chain. Added: funding rates, NUPL, exchange flows, ETF flows, stablecoin supply, BTC dominance/season indicators.*
