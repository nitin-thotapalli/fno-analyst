# F&O Analyst — Development Roadmap

**State:** Proposed, not scheduled. Milestones below describe exploratory work, not completed tasks.

## 01. Define one example question about a NIFTY option chain and its exact inputs.

- [ ] Document evidence or outputs.
- [ ] Review assumptions and known limitations before advancing.

## 02. Build a small synthetic CSV dataset and data dictionary; no live API dependency.

- [ ] Document evidence or outputs.
- [ ] Review assumptions and known limitations before advancing.

## 03. Implement deterministic OI and payoff calculations in a Jupyter notebook.

- [ ] Document evidence or outputs.
- [ ] Review assumptions and known limitations before advancing.

## 04. Cross-check Greeks and scenario P&L against a trusted reference implementation.

- [ ] Document evidence or outputs.
- [ ] Review assumptions and known limitations before advancing.

## 05. Add a minimal dashboard and explain observations, assumptions and limits.

- [ ] Document evidence or outputs.
- [ ] Review assumptions and known limitations before advancing.

## 06. Evaluate real data access, licensing and refresh limits before considering live feeds.

- [ ] Document evidence or outputs.
- [ ] Review assumptions and known limitations before advancing.

## Definition of a useful first prototype

A user can inspect one grounded example end-to-end, understand its inputs and assumptions, reproduce the output, and identify what is still unknown. A prototype is not a production-ready or fully validated system.

## Open decisions

- [ ] Which data provider or broker can lawfully supply the desired contracts and history?
- [ ] Are the use cases end-of-day research, intraday monitoring, or personal position analytics?
- [ ] How should missing quotes, illiquid strikes and stale snapshots be handled?
- [ ] Which strategy structures are first: single legs, spreads or other defined-risk positions?
