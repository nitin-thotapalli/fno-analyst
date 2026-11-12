# F&O Analyst — Proposed Architecture

**Product boundary:** A read-only personal derivatives research and scenario-analysis system. No automated trade submission, investment guarantees or unsupported “best option” claims.

```text
Historical / delayed permitted market data   User-approved portfolio snapshot
                   ↓                                   ↓
       Data quality + canonical contract identifiers + user risk policy
                   ↓                                   ↓
       Option/futures analytics                Portfolio risk aggregation
                   └──────────────┬────────────────────┘
                                  ↓
                   Candidate strategy simulation
                                  ↓
               Stress tests + independent validation
                                  ↓
                 Human-readable review memo
                         (including no trade)
```

## Components and responsibilities

| Component | Inputs | Outputs / controls |
| --- | --- | --- |
| Market adapter | Licensed/historical spot, futures, option data, exchange specs | Source, time, quote, strike, expiry, multiplier; reject untrusted input |
| Position importer | User-approved holdings and portfolio limits | Normalized positions, cash, concentration, margin assumptions |
| Contract normalization | Underlying, right, strike, expiry, lot, exchange, series | Unique contract keys with versioned specifications |
| Deterministic analytics | Quotes, conventions, rates/dividends, vol inputs | OI metrics, IV, Greeks, theoretical values, payoffs, sensitivities |
| Portfolio engine | Positions, candidate strategy, model assumptions | Baseline and incremental exposures, scenario P&L |
| Strategy comparator | Eligible contracts, risk policy and scenario set | Comparable candidate risk reports and rejection reasons |
| Research interface | Validated analytics and thesis notes | Explanations, visible assumptions, supporting snapshots, “no trade” |
| Audit / journal | Time-stamped analysis and human review | Reproducible decisions and post-hoc review |

## Critical distinctions

- **Payoff at expiry** is not the same as mark-to-market **value before expiry**.
- **Market premium** is not the same as **model-implied/theoretical price**.
- **Margin requirement** is not necessarily the **maximum economic loss**.
- **Open interest** is not a stand-alone directional prediction.
- A point-in-time quote is not evidence that a real order could be executed at that price.

## Minimum data contract

For each contract: exchange, underlying, instrument type, option side, strike, expiry, lot multiplier, settlement convention, bid/ask (if available), timestamp, spot/futures reference, volume/OI and provenance. Missing critical fields must fail validation instead of silently generating analytics.

A portfolio record requires position quantity/direction, acquisition price if relevant, capital/margin context, update time and user-defined limits. Use synthetic holdings before testing personal data.

## Mathematical and user-safety tests

1. Expiry payoff and net P&L across known reference cases; verify treatment of premium and transaction costs.
2. Greeks and implied volatility checked against an independent reference under documented conventions.
3. Stress tests for volatility shift, gap moves, time decay and liquidity cost.
4. Incremental portfolio risk measured **relative to the existing positions**, not just isolated trades.
5. Policy rejects stale contracts, invalid lots, unbounded exposure incompatible with user limits, and incomplete data.
6. Every human-facing observation distinguishes **fact, model output and hypothesis**.

## First milestone

Implement a notebook with deterministic option-chain data, contract mappings, a synthetic portfolio, two defined-risk candidate strategies, and a no-trade comparator. Deliver an independently checked calculation and a reproducible review memo.

## Deferred decisions

- Permitted end-of-day or intraday data provider, entitlements and refresh frequency.
- Which contract conventions and pricing models are defensible for the selected market.
- Whether a conversational explanation layer improves understanding beyond a good notebook.
- Whether live monitoring is necessary; **execution is not part of the current plan**.
