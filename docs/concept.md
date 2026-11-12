# F&O Analyst — Original Concept & Scope

> **Current direction:** This file preserves the original exploration. The [README](../README.md) now defines a **personal, portfolio-aware capital-markets research assistant** that explains contracts, compares risk-defined trade ideas and can conclude **no trade**. It is independent of Project Matrix and is not a production trading signal or execution system.

## Original idea (from Notion)

> Imagine opening an application and asking: “What's happening in NIFTY options today? Is volatility increasing? Where is open interest concentrated?”
>
> The application could provide option-chain, open-interest, volatility, Greeks, futures, strategy simulation, personal portfolio analysis, and AI explanations of calculations. The system should separate observations from predictions: high call open interest does not guarantee that the market will fall.

*Condensed for readability; the capability table appears below.*

## Problem hypothesis

Options and futures data are distributed across contracts, expiries, strikes and risk measures. An analyst needs a consistent way to inspect the data and understand what the numbers do—and do not—imply.

## Intended audience (hypothesis)

A personal analytical workbench for researching Indian index derivatives, initially NIFTY (hypothesis).

## Scope to investigate

- Option chain: calls, puts, strikes, expiries and contract identifiers.
- Open interest: concentration, changes and volume, with snapshot timestamps.
- Volatility: implied and historical volatility, term structure and changes where supported.
- Option Greeks: delta, gamma, theta and vega, tied to documented assumptions.
- Futures: price, volume, open interest and basis.
- Strategy simulator: payoff diagram, breakeven, bounded/unbounded loss characterization and scenario P&L.
- Personal positions: exposure, concentration, expiry risk, and what-if scenarios.
- Natural-language explanations grounded in computed results and data provenance.

## What this project does **not** yet provide

- Live exchange connectivity, licensed market data or automated trading.
- A predictive trading signal or a recommendation to buy or sell contracts.
- Validated pricing, Greeks or P&L without test data and reference checks.

## Questions to resolve

- [ ] Which data provider or broker can lawfully supply the desired contracts and history?
- [ ] Are the use cases end-of-day research, intraday monitoring, or personal position analytics?
- [ ] How should missing quotes, illiquid strikes and stale snapshots be handled?
- [ ] Which strategy structures are first: single legs, spreads or other defined-risk positions?

## Source and provenance

