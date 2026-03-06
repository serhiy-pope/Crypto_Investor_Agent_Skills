# Company Card
### Modules 1–3 · One file per ticker · Update after reports/events

---

> **How to use**
> Filled once when first studying the company.
> Updated after quarterly report or significant corporate events.
> Not tied to a trade — this is a business profile that outlives any position.

---

## BLOCK 0 — SOURCES AND DATA QUALITY (anti‑hallucination)

### Template
```
Ticker: ___
Fill date: ____-__-__
Reporting currency: ___

Primary sources (links/names):
1) ___
2) ___

Data quality:
[ ] numbers with units (%, $, EUR, bps)
[ ] period specified (TTM/FY/quarter)
[ ] if estimated → marked as estimate
```

### Example: ASML
```
Ticker: ASML
Fill date: 2025-02-16
Reporting currency: EUR

Sources:
1) ASML FY 2024 Annual Report
2) Q4 2024 Earnings Call Transcript
3) TSMC Q4 2024 Capex Guidance

Data quality:
[✓] numbers with units
[✓] period specified (FY2024)
[✓] estimates — marked
```

---

## BLOCK 1 — IDENTIFICATION

| Parameter | Template | Example: ASML |
|---|---|---|
| Ticker | `___` | `ASML` |
| Full name | `___` | `ASML Holding N.V.` |
| Exchange | `___` | `Nasdaq / Euronext Amsterdam` |
| Sector / Industry | `___` | `Technology / Semiconductor Equipment` |
| Country of incorporation | `___` | `Netherlands` |
| Market capitalization | `$___` | `~$290B` |
| Portfolio class | `GREEN / YELLOW / ORANGE` | `GREEN` |
| Last update date | `____-__-__` | `2025-02-16` |

---

## BLOCK 2 — BUSINESS MODEL AND REVENUE SOURCE

### Template
```
WHAT THE COMPANY DOES (1–2 sentences): ___

HOW IT MAKES MONEY (revenue segments):
  Segment 1: ___ → ___% of revenue
  Segment 2: ___ → ___%
  Segment 3: ___ → ___%

NORTH STAR METRIC: ___

CLIENTS (top 3):
  1. ___ — ~___% of revenue
  2. ___ — ~___%
  3. ___ — ~___%

CYCLICALITY: cyclical / non-cyclical / mixed. Reason: ___

GEOGRAPHY:
  US: ___%  |  Europe: ___%  |  Asia: ___%  |  China: ___%
```

### Example: ASML
```
WHAT THE COMPANY DOES:
The world's only manufacturer of EUV lithography systems — equipment for
producing chips at 7nm and below. Without ASML machines it is impossible
to manufacture advanced processors, GPUs and memory.

HOW IT MAKES MONEY:
  EUV systems (new):       ~55% of revenue → main growth driver
  DUV systems (mature):    ~25% → stable flow, China exposure
  Service and parts:      ~20% → high-margin recurring flow

NORTH STAR METRIC:
  Backlog (order book) — leading revenue indicator for 2–3 years.
  Current: ~€36–40B. Y/y decline — first warning signal.

CLIENTS:
  1. TSMC       — ~40% of revenue
  2. Samsung    — ~20%
  3. Intel      — ~15%  (high concentration — key risk)

CYCLICALITY:
  Mixed. EUV orders are long-term (2–3 years from order to delivery),
  but depend on foundry capex plans, which are cyclical.

GEOGRAPHY:
  Taiwan: ~40% | Korea: ~25% | China: ~15% | Europe: ~10% | US: ~5%
```

---

## BLOCK 3 — FINANCIAL METRICS

### Template
```
Period: TTM / FY____ / Q____

Revenue:         $___  (y/y growth: ___%)
Gross Margin:    ___%  (trend: ↑ / → / ↓)
EBITDA Margin:   ___%
Net Margin:      ___%
FCF:             $___  (FCF Margin: ___%)
ROIC:            ___%  (WACC estimate: ___%)
ROIC vs WACC:    spread +___% → creates / destroys value

Balance sheet:
  Cash:          $___
  Debt:          $___
  Net Debt/EBITDA: ___x

Valuation:
  Forward P/E:   ___x  (hist. norm: ___x)
  EV/EBITDA:     ___x
  P/FCF:         ___x
  Valuation Zone: V_low / V_fair / V_high

Dynamics (3-year trend):
  Revenue CAGR 3Y:  ___%
  FCF CAGR 3Y:     ___%
  EPS CAGR 3Y:     ___%
```

### Example: ASML (FY 2024)
```
Revenue:         €28.3B  (y/y growth: +14%)
Gross Margin:    ~51%    (trend: →)
EBITDA Margin:   ~32%
Net Margin:      ~27%
FCF:             ~€6B    (FCF Margin: ~21%)
ROIC:            ~25–30% (WACC estimate: ~8–9%)
ROIC vs WACC:    spread +17–21% → confidently creates value

Balance sheet:
  Cash: ~€7B | Debt: ~€4B | Net Debt/EBITDA: negative (net cash)

Valuation (price ~$720):
  Forward P/E: ~30x (norm 25–35x) | EV/EBITDA: ~21x | P/FCF: ~30x
  Zone: V_fair

Dynamics: Revenue CAGR 3Y ~18% | FCF CAGR 3Y ~22% | EPS CAGR 3Y ~20%
```

---

## BLOCK 3B — FAIR VALUE (Bear / Base / Bull)

### Template

| Scenario | Fair Value | Key assumptions | Upside/Downside |
|---|---|---|---|
| **Bear** | $_____ | ___ | ___% |
| **Base** | $_____ | ___ | ___% |
| **Bull** | $_____ | ___ | ___% |

### Example: ASML
| Scenario | Fair Value | Assumptions | vs $720 |
|---|---|---|---|
| **Bear** | $520 | Capex −20%, DUV restrictions, P/E 22x | −28% |
| **Base** | $820 | Guidance met, backlog stable, P/E 30x | +14% |
| **Bull** | $950 | TSMC capex $38B+, EUV >60%, P/E 35x | +32% |

**What breaks the thesis:** Backlog <€25B + emergence of EUV competitor → exit unconditionally.

---

## BLOCK 3C — WHAT'S ALREADY IN THE PRICE

### Template
```
1. Revenue growth implied: ___% → realistic / aggressive / conservative
2. Margin trajectory implied: margin → ___% → achieved / required / unrealistic
3. Key market assumption: ___

Conclusion:
- My thesis aligns with / above / below market
```

### Example: ASML
```
1. Revenue growth implied: ~10–12% per year → conservative (company grows faster)
2. Margin implied: ~51% gross → achieved
3. Market is pricing in: stable foundry capex, no worsening of restrictions

Conclusion: my Base aligns with market. For upside, transition to Bull needed.
```

---

## BLOCK 4 — MOAT AND COMPETITION

### Template
```
MOAT TYPE:
  [ ] patents/brand/licenses
  [ ] switching costs
  [ ] network effects
  [ ] cost advantage
  [ ] efficient scale
  [ ] regulatory barrier

Strength: strong / medium / weak
Horizon: ___ years
Threat: ___

KSF (max 2): 1) ___  2) ___

Competitors:
  Company | Share | Threat
```

### Example: ASML
```
MOAT TYPE:
  [✓] Patents — 30+ years R&D, thousands of EUV patents
  [✓] Efficient scale — monopoly: only EUV manufacturer in the world
  [✓] Switching costs — fab processes are built around ASML

Strength: very strong | Horizon: 10–15+ years | Threat: alternative lithography

KSF: 1) Backlog (demand visibility)  2) EUV share of revenue (quality mix)

Competitors:
  ASML  | ~100% EUV | — (monopoly)
  Nikon | ~10% DUV  | low
  Canon | ~5% DUV   | low
  → No EUV competition visible in 10-year horizon
```

---

## BLOCK 5 — GROWTH DRIVERS AND CATALYSTS

```
Top 3 drivers: 1) ___  2) ___  3) ___
Catalysts (3–12 months): ___
```

---

## BLOCK 6 — RISKS AND INVALIDATION TRIGGERS

### Template
```
Risk 1 (high): ___
  Indicator: ___
  Invalidation trigger: ___

Fundamental stop (for GREEN):
✗ ___
✗ ___
```

### Example: ASML
```
Risk 1 (high): Export restrictions on China
  Indicator: regulatory news, China share of revenue
  Invalidation trigger: loss of >30% revenue due to restrictions

Risk 2 (medium): Foundry capex cycle
  Indicator: TSMC and Samsung capex guidance
  Invalidation trigger: backlog declines >30% y/y for two consecutive quarters

Risk 3 (medium): Concentration — TSMC ~40% of revenue
  Indicator: TSMC financial health
  Invalidation trigger: TSMC cuts capex >40% y/y

Risk 4 (tail): Taiwan geopolitics
  Indicator: escalation  →  emergency review

Fundamental stop:
✗ ROIC < 18% for two consecutive quarters
✗ Gross Margin < 45%
✗ Backlog < €30B for two consecutive quarters
✗ Export restrictions >30% of revenue

Event markers (quarterly):
[ ] ASML report: revenue/margin/backlog/guidance
[ ] TSMC capex guidance
[ ] Chip equipment export regulation
[ ] High-NA EUV — positive marker
```

---

## BLOCK 7 — MANAGEMENT AND CAPITAL ALLOCATION

### Template
```
CEO/CFO: ___ (tenure, decisions)
Quality: [ ] Delivers guidance  [ ] Honest about risks  [ ] Long-term thinking  [ ] Insider ownership

Capital allocation:
  Buyback: yes/no → $___/year
  Dividends: yes/no → yield ___%
  M&A: active/passive
  R&D: ___% of revenue | Capex: ___% of revenue

Assessment: creates / neutral / destroys value
```

### Example: ASML
```
CEO: Christophe Fouquet (since 2024), previously Peter Wennink (20+ years)

[✓] Delivers guidance — strong track record
[✓] Honest about risks — openly discuss China
[✓] Long-term thinking — R&D ~15% even in downturns
[✓] Insider ownership — significant among top management

Buyback: €5–6B/year | Dividends: yield ~1.0–1.2% (growing)
M&A: passive | R&D: ~15% | Capex: ~8–10%

Assessment: creates value. Buyback + dividend growth + high R&D =
compounding formula. No value-destructive M&A.
```

---

## BLOCK 8 — MONITORING

```
Quarterly: [ ] report  [ ] north star  [ ] 1–2 key risks
Event triggers: ___
```

---

## BLOCK 9 — FALSE PRECISION CHECK

| Parameter | Value | Confidence | Source |
|---|---|---|---|
| Revenue growth | ___ | ☐ High ☐ Medium ☐ Low | |
| Net Margin | ___ | ☐ High ☐ Medium ☐ Low | |
| Target multiple | ___ | ☐ High ☐ Medium ☐ Low | |
| TAM / penetration | ___ | ☐ High ☐ Medium ☐ Low | |
| Competitive position 3–5 years | ___ | ☐ High ☐ Medium ☐ Low | |

**Rule:** ≥2 parameters = "Low" → GREEN class prohibited. YELLOW only (small size) or PASS.

---

## SUMMARY

```
ONE PHRASE: ___
CLASS: ___   STATUS: Active / On hold / Closed
Next update: ____-__-__ (after ___ report)
```

### Example: ASML
```
ASML — structural monopoly on technology without which it is impossible to
produce any advanced chip on the planet; buying time and quality.

CLASS: GREEN   STATUS: Active
Next update: after Q1 2025 report (April 2025)
```

---

*Version 3.0 · ASML examples restored for each block. Added: Fair Value + "What's in the price" + False Precision + Sources.*
