# Asset Card — Crypto
### Modules 1–3 · One file per token/protocol · Update after major events

---

> **How to use**
> Filled once when first studying the asset.
> Updated after major protocol upgrades, tokenomics changes, or significant on-chain events.
> Not tied to a trade — this is a protocol profile that outlives any position.

---

## BLOCK 0 — SOURCES AND DATA QUALITY (anti‑hallucination)

### Template
```
Ticker: ___
Fill date: ____-__-__
Reporting denomination: USD / BTC / ETH

Primary sources (links/names):
1) ___
2) ___

Data quality:
[ ] numbers with units (%, $, tokens, bps)
[ ] period specified (date/timeframe)
[ ] if estimated → marked as estimate
[ ] on-chain data source specified (Glassnode/DeFiLlama/Dune/etc.)
```

### Example: ETH
```
Ticker: ETH
Fill date: 2026-03-06
Reporting denomination: USD

Sources:
1) Ethereum Foundation blog + EIPs
2) DeFiLlama (TVL data)
3) ultrasound.money (burn/issuance)
4) Glassnode (on-chain metrics)

Data quality:
[✓] numbers with units
[✓] period specified
[✓] estimates — marked
[✓] on-chain sources specified
```

---

## BLOCK 1 — IDENTIFICATION

| Parameter | Template | Example: ETH |
|---|---|---|
| Ticker | `___` | `ETH` |
| Full name | `___` | `Ethereum` |
| Category | `___` | `L1 Smart Contract Platform` |
| Consensus | `___` | `Proof of Stake (since Sep 2022)` |
| Chain / Network | `___` | `Ethereum Mainnet` |
| Market capitalization | `$___` | `~$350B` |
| Portfolio class | `GREEN / YELLOW / ORANGE` | `GREEN` |
| Smart contract audit | `yes/no/N/A` | `N/A (base protocol)` |
| Last update date | `____-__-__` | `2026-03-06` |

---

## BLOCK 2 — VALUE PROPOSITION AND REVENUE SOURCE

### Template
```
WHAT IT IS (1–2 sentences): ___

HOW VALUE IS CAPTURED:
  Mechanism 1: ___ → impact on token: ___
  Mechanism 2: ___ → impact on token: ___
  Mechanism 3: ___ → impact on token: ___

NORTH STAR METRIC: ___
  (The single most important metric to track. Decline = first warning signal.)

DEMAND DRIVERS (top 3):
  1. ___ — contribution: ___
  2. ___ — contribution: ___
  3. ___ — contribution: ___

CYCLICALITY: high / medium / low vs BTC. Reason: ___

ECOSYSTEM SIZE:
  Active addresses (daily): ___
  TVL (if applicable): $___
  Developer count / GitHub commits: ___
```

### Example: ETH
```
WHAT IT IS:
Ethereum is the dominant programmable blockchain — the settlement layer for DeFi,
stablecoins, NFTs, and tokenized real-world assets. ETH is the gas token and staking
collateral of the network.

HOW VALUE IS CAPTURED:
  Gas fees (EIP-1559 burn): ETH paid as fees is permanently burned → deflationary pressure
  Staking yield: ~4% APY paid to validators → incentivizes holding and locking supply
  L2 settlement: L2s post data/proofs to mainnet → base demand floor

NORTH STAR METRIC:
  Net issuance rate — if ETH turns inflationary (burn < issuance), supply thesis weakens.
  Current: ultrasound.money shows net issuance daily.

DEMAND DRIVERS:
  1. DeFi TVL — $50–60B deployed in protocols using ETH as collateral
  2. L2 ecosystem — Arbitrum, Base, Optimism, zkSync generate L1 settlement demand
  3. Institutional ETF demand — ETH ETFs approved, ongoing institutional accumulation

CYCLICALITY: medium vs BTC. ETH amplifies BTC moves (beta ~1.3–1.8 vs BTC).

ECOSYSTEM:
  Active addresses (daily): ~450–500k
  DeFi TVL: ~$50–60B
  Developer count: #1 by GitHub commits across all blockchains
```

---

## BLOCK 3 — TOKENOMICS

### Template
```
SUPPLY:
  Total supply: ___
  Circulating supply: ___
  Max supply: ___  (or: uncapped)
  Current issuance rate: ___% annual
  Issuance type: Inflationary / Deflationary / Neutral

INFLATION / DEFLATION MECHANICS:
  Burn mechanism: yes/no → description: ___
  Staking lock-up: ___% of supply staked
  Vesting / unlock schedules: ___

DISTRIBUTION:
  Team / Foundation: ___% (vesting: ___)
  Investors / VCs: ___% (vesting: ___)
  Public / Community: ___% 
  Treasury: ___%

RED FLAGS:
  [ ] Large upcoming unlock (>5% supply in <90 days)
  [ ] High VC concentration
  [ ] Excessive team allocation (>25%)
  [ ] No burn or deflationary mechanic
  [ ] Inflationary at current activity levels
```

### Example: ETH
```
SUPPLY:
  Total supply: ~120M ETH (dynamic)
  Circulating: ~120M ETH
  Max supply: uncapped (but effectively deflationary at current activity)
  Current issuance: ~0.5–1.0% annual gross; net ~−0.5% (deflationary) at current fee levels
  Issuance type: Deflationary (post-Merge at current usage)

INFLATION / DEFLATION:
  Burn: YES — EIP-1559 burns base fee in each transaction
  Staking lock-up: ~28% of supply (~33M ETH staked)
  Vesting: No cliff unlocks — supply is earned by validators

DISTRIBUTION:
  No traditional VC allocation (launched 2015 via ICO)
  Ethereum Foundation: ~1% of supply
  Community/holders: 99%+

RED FLAGS: None at current configuration.
  [✓] No large upcoming unlock
  [✓] Minimal Foundation share
  [✓] Burn mechanism active
  [✓] Deflationary at current activity
```

---

## BLOCK 4 — ON-CHAIN METRICS AND VALUATION

### Template
```
VALUATION MULTIPLES:
  NVT Ratio (Mkt Cap / 30d Transaction Volume): ___x   (hist. range: ___–___x)
  P/TVL (Mkt Cap / DeFi TVL, if applicable): ___x       (hist. range: ___–___x)
  P/Fees (Mkt Cap / Annualized Protocol Fees): ___x      (hist. range: ___–___x)
  Relative to BTC (ETH/BTC ratio): ___                   (hist. range: ___–___)

ON-CHAIN HEALTH:
  Active addresses (30d trend): ↑ / → / ↓
  Transaction count (30d trend): ↑ / → / ↓
  Exchange netflows (7d): inflow/outflow $___M   (inflow = selling pressure)
  Long-term holder supply %: ___% (rising = accumulation)

CYCLE POSITION:
  BTC cycle phase: Accumulation / Early Bull / Mid Bull / Late Bull / Bear
  This asset vs BTC YTD: +/−___% (alpha/beta vs BTC)
```

### Example: ETH
```
VALUATION MULTIPLES (illustrative — verify current):
  NVT Ratio: ~40–60x   (bear: 20–40x, fair: 40–80x, expensive: >100x)
  P/TVL: ~7x           (bear: 3–5x, fair: 5–10x, expensive: >15x)
  P/Fees: ~25x         (bear: 10–15x, fair: 15–35x, expensive: >50x)
  ETH/BTC ratio: ~0.05 (range: 0.03–0.08; middle of range)

ON-CHAIN HEALTH:
  Active addresses: ~450–500k daily → neutral trend
  Exchange netflows: slight outflow → mild accumulation signal
  Long-term holder supply: ~65% → stable
  Staking rate: ~28% → high, supply locked

CYCLE POSITION:
  Mid-bull (estimated 12–18 months post-halving)
  ETH/BTC: ~0.05 (mid-range, not at altseason peak)
```

---

## BLOCK 4B — FAIR VALUE (Bear / Base / Bull)

### Template

| Scenario | Fair Value | Key assumptions | Upside/Downside |
|---|---|---|---|
| **Bear** | $_____ | ___ | ___% |
| **Base** | $_____ | ___ | ___% |
| **Bull** | $_____ | ___ | ___% |

### Example: ETH
| Scenario | Fair Value | Assumptions | vs $3,200 |
|---|---|---|---|
| **Bear** | $1,800 | DeFi TVL −40%, bear market, P/TVL ~4x | −44% |
| **Base** | $4,000 | Stable TVL, ETF flows continue, P/TVL ~7x | +25% |
| **Bull** | $7,000 | DeFi expansion, L2 surge, institutional ETF wave, P/TVL ~12x | +119% |

**What breaks the thesis:** TVL collapse + net inflation return → exit unconditionally.

---

## BLOCK 5 — MOAT AND COMPETITIVE POSITION

### Template
```
MOAT TYPE:
  [ ] Network effects (users attract users)
  [ ] Developer ecosystem (tools, composability)
  [ ] Protocol composability (DeFi money legos)
  [ ] Liquidity moat (deepest DEX/CEX markets)
  [ ] Brand / first-mover
  [ ] Regulatory positioning (clear legal status)

Strength: strong / medium / weak
Horizon: ___ years
Main threat: ___

Key Success Factors (max 2): 1) ___  2) ___

Competitors:
  Protocol | TVL/Users | Threat level
```

### Example: ETH
```
MOAT TYPE:
  [✓] Network effects — most dApps, users, and liquidity are on Ethereum
  [✓] Developer ecosystem — largest developer community by far
  [✓] Protocol composability — DeFi protocols are deeply interconnected
  [✓] Liquidity moat — deepest on-chain liquidity

Strength: very strong | Horizon: 5–10+ years | Main threat: alternative L1 fragmentation

Key Success Factors:
  1) Developer retention (new protocols choose Ethereum)
  2) L2 ecosystem health (adoption without fragmenting mainnet security)

Competitors:
  Solana    | ~$8–10B TVL  | High (speed, UX, growing developer activity)
  BNB Chain | ~$5–7B TVL   | Medium (centralized, lower developer quality)
  TON       | Growing       | Medium (Telegram distribution advantage)
  → Ethereum retains 55–60%+ of total DeFi TVL despite competition
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

### Example: ETH
```
Risk 1 (high): L2 fee cannibalization
  Indicator: ETH base fee trending toward zero; burn rate collapsing
  Invalidation trigger: Net issuance turns >2% annually for 3+ months

Risk 2 (high): Regulatory classification as security (US/EU)
  Indicator: SEC/CFTC enforcement actions, ETF suspension
  Invalidation trigger: Formal security classification in major jurisdiction → immediate review

Risk 3 (medium): DeFi TVL collapse
  Indicator: Total DeFi TVL falling below $20B
  Invalidation trigger: TVL <$20B for two consecutive months

Risk 4 (medium): Competitor ecosystem disruption
  Indicator: ETH developer share falling below 40% of total
  Invalidation trigger: ETH loses majority of new protocol deployments for 2 consecutive quarters

Risk 5 (tail): Smart contract layer exploit
  Indicator: Critical vulnerability in consensus layer
  Invalidation trigger: Consensus layer exploit → emergency review

Fundamental stop:
✗ Net ETH issuance > +2% annually for 3+ months (inflation thesis broken)
✗ DeFi TVL < $20B for two consecutive months
✗ Regulatory prohibition as security in US + EU simultaneously
✗ Developer activity (GitHub commits) drops >50% in 6 months

Event markers:
[ ] Ethereum upgrades (Dencun, Pectra, etc.)
[ ] ETH ETF weekly flows (Bloomberg/CoinGlass)
[ ] DeFi TVL weekly (DeFiLlama)
[ ] SEC/regulatory news
[ ] Competitor major protocol launches
```

---

## BLOCK 7 — TEAM / FOUNDATION AND GOVERNANCE

### Template
```
Core team / Foundation: ___
Development process: ___
Governance: ___
Decentralization level: high / medium / low
Key person risk: ___
```

### Example: ETH
```
Core: Ethereum Foundation (EF) coordinates research; Vitalik Buterin as lead researcher
Development: Open-source, multiple client teams (Geth, Erigon, Besu, Nethermind)
Governance: EIP (Ethereum Improvement Proposal) process — rough consensus, no token voting
Decentralization: High — no single entity can change protocol without broad consensus
Key person risk: Low-Medium — Vitalik has outsized influence on narrative and direction,
                 but protocol changes require client team consensus
```

---

## BLOCK 8 — MONITORING

```
Weekly: [ ] on-chain issuance rate  [ ] DeFi TVL  [ ] exchange flows
Monthly: [ ] developer activity  [ ] L2 ecosystem growth  [ ] ETF flows
Event triggers: ___
```

---

## BLOCK 9 — FALSE PRECISION CHECK

| Parameter | Value | Confidence | Source |
|---|---|---|---|
| DeFi TVL | ___ | ☐ High ☐ Medium ☐ Low | |
| Issuance/burn rate | ___ | ☐ High ☐ Medium ☐ Low | |
| Fair Value target | ___ | ☐ High ☐ Medium ☐ Low | |
| P/TVL historical range | ___ | ☐ High ☐ Medium ☐ Low | |
| Competitive position 3–5 years | ___ | ☐ High ☐ Medium ☐ Low | |

**Rule:** ≥2 parameters = "Low" → GREEN class prohibited. YELLOW only (small size) or PASS.

---

## SUMMARY

```
ONE PHRASE: ___
CLASS: ___   STATUS: Active / On hold / Closed
Next update: ____-__-__ (after ___ event/upgrade)
```

### Example: ETH
```
ETH — deflationary smart contract platform with dominant DeFi moat, staking-aligned
supply mechanics, and L2 ecosystem flywheel; accumulating mid-cycle.

CLASS: GREEN   STATUS: Active
Next update: after Pectra upgrade completion + next ETH ETF flow data
```

---

*Version 1.0 · Crypto adaptation. Replaced: financial statements → tokenomics + on-chain metrics. Replaced: ROIC/FCF → NVT/P/TVL/P/Fees. Added: custody info, network effects moat framework, fundamental stop triggers.*
