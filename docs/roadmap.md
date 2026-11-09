# F&O Analyst — Research & Development Roadmap

**Status:** Experiment plan, not an implemented platform or proven investment approach.

| Gate | Deliverable | Acceptance condition |
| --- | --- | --- |
| 01 — Learning scope | Written derivatives question and contract glossary | Can explain payoff, time/volatility effects and portfolio context |
| 02 — Data contract | Documented historical/delayed NIFTY snapshot and synthetic portfolio | Dates, strikes, lot sizes, rights and provenance reconciled |
| 03 — Deterministic math | Notebook with option/futures P&L and selected Greeks | Reference tests pass, including expiry and unusual inputs |
| 04 — Portfolio view | Baseline positions plus incremental strategy exposure | Aggregate risk differs correctly when a position is added |
| 05 — Comparison | Two defined-risk alternatives and **no trade** | Same scenarios, assumptions, estimated costs and risk limits |
| 06 — Human explanation | Short decision memo and evidence-linked calculations | Reviewer can reproduce results and identify missing information |
| 07 — Learning loop | Journal of hypothetical cases and errors | No hindsight selection or false claims of live returns |
| 08 — Scope review | Decide whether permitted live data adds enough value | Data quality, availability, rights, operating costs and safety assessed |

## Evaluation protocol

- Test on a **small fixed set** of historical or synthetic scenarios, including rising/falling underlying, IV shifts and expiry effects.
- Verify formulas with independent references and known payoff identities.
- Compare time to complete a documented review against the manual spreadsheet workflow.
- Track critical contract mapping errors, stale snapshots, unexplained numbers, scenario completeness and risk policy breaches.
- Do not report backtested profitability, Sharpe or hit rates as real performance; avoid selecting only favourable retrospective outcomes.

## Hard constraints

- [ ] No automated order placement.
- [ ] No fabricated broker balances, price quotes or probabilities.
- [ ] No unsuitable candidate presented as acceptable when data or user risk budget is missing.
- [ ] Market data access and redistribution permissions documented before using feeds.
- [ ] Explicit human judgment, with **no trade** an acceptable end state.
- [ ] Unbounded or leveraged risk must be clearly disclosed where relevant.

## Open decisions

Which contracts first? Which permitted data source and refresh cadence? What user risk constraints are necessary? What mathematics need independent testing? Is a notebook sufficient before an agent is considered?
