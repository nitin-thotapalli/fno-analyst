# F&O Analyst

**Understand derivatives. Evaluate opportunities. See the risk before making a decision.**

F&O Analyst is a proposed **personal futures-and-options research assistant**. I want to understand derivatives more deeply and build a disciplined way to examine market conditions, contracts, strategies, and my overall portfolio **before deciding whether any trade is worth considering**.

## Why F&O Analyst?

A futures or options decision is not just a question of whether an index or stock might rise or fall. The outcome depends on the **underlying asset, contract terms, strike, expiry, implied volatility, time decay, liquidity, transaction costs, and portfolio exposure**.

The information is fragmented across option chains, futures quotes, historical prices, volatility measures, broker screens, and personal holdings. Even after collecting it, the difficult part remains: **What does this information mean for me, given what I already own, how much I can lose, and the alternatives available today?**

I want to move from isolated market observations and impulsive contract selection toward a repeatable, evidence-based decision process.

The central question is:

**Given current market data, my existing positions, and a defined risk budget, which strategies deserve investigation today—and when is doing nothing the better decision?**

The project is intended to **guide research and decision-making**, not to promise accurate predictions or guarantee profitable trades.

## Who is it for?

Initially, **me**: an individual learning Indian futures and options, beginning with liquid index contracts such as NIFTY. The scope can expand only after the calculations, data quality, and workflow are validated.

## Questions the assistant should answer

1. **What is happening in the market?** Summarize the underlying price, futures basis, volume, open interest, volatility, and relevant changes, with timestamps.
2. **What do the contracts mean?** Explain expiry, lot size, strike, premium, margin, settlement, and payoff mechanics.
3. **What risks do I already have?** Aggregate portfolio positions, directional exposure, concentration, Greeks, margin use, and expiry-related risks.
4. **Which ideas are worth testing?** Screen defined strategies against a market hypothesis, liquidity constraints, capital, and risk limits.
5. **What could go wrong?** Calculate scenario P&L, maximum or potentially unbounded losses, breakevens, sensitivity to volatility and time, and transaction costs.
6. **Should I trade at all?** Compare candidates with a no-trade baseline and flag missing evidence, unsuitable risk, or excessive concentration.

## Proposed decision workflow

| Stage | What happens | Intended output |
| --- | --- | --- |
| 1. Portfolio context | Read user-approved holdings, cash, exposures, and limits | Current risk picture |
| 2. Market snapshot | Retrieve timestamped underlying, futures, options, and volatility data | Verified market context |
| 3. Hypothesis | State a directional, volatility, or range-bound view and its uncertainty | Explicit thesis, not a prediction |
| 4. Candidate generation | Identify eligible contracts and common defined-risk strategies | Shortlist of possibilities |
| 5. Risk and scenario analysis | Calculate payoff, Greeks, margin, liquidity, slippage, and stress cases | Comparable risk/reward profiles |
| 6. Decision support | Explain trade-offs, conflicts with portfolio limits, and no-trade reasons | Research memo for human review |
| 7. Learning loop | Record the original thesis and compare outcomes afterward | Decision journal and error analysis |

**No order is placed by the proposed assistant.** Any eventual broker integration or execution capability would be a separate, explicitly authorized and safety-reviewed phase.

## What the analytical workbench could contain

### Market and contract intelligence

- Underlying spot price and futures price; basis and expiry structure.
- Option-chain strikes, premiums, bid/ask spreads, volume, open interest, and timestamps.
- Implied versus historical volatility, skew, and term structure where reliable data exist.
- Contract specifications, expiry dates, lot sizes, settlement rules, and exchange notices.

### Portfolio-aware risk

- Position-level and aggregated delta, gamma, theta, and vega with model assumptions.
- Directional and correlated exposure across holdings.
- Margin and collateral needs; liquidity and forced-exit risks.
- Stress tests for underlying-price moves, volatility changes, and passage of time.
- Position sizing relative to a **user-defined maximum acceptable loss**, not an AI-generated risk appetite.

### Strategy evaluation

- Long/short futures, long options, vertical spreads, and other strategies only after their risks are correctly modeled.
- Payoff at expiry **and** scenario values before expiry.
- Breakeven, net debit/credit, maximum gain/loss where mathematically bounded, and cases with open-ended exposure.
- Fees, taxes, spread, slippage, and execution feasibility.
- Comparison with a **no-trade** alternative.

### Explanations and research notes

Every conclusion should show **data timestamp, source, calculations, assumptions, scenario conditions, and uncertainty**. A natural-language agent should explain verified outputs, not invent prices, Greeks, or probabilities.

## Example question

> I already have a bullish position and limited remaining risk capacity. What would adding a NIFTY call spread do to my exposure if the index falls 3%, rises 2%, or implied volatility drops?

A useful response would show the **incremental portfolio exposure**, scenario P&L, capital required, and relevant assumptions. It could also conclude that the candidate is unsuitable or that no trade is preferable.

## First practical milestone

Build a **Jupyter-based research notebook** using a documented historical or delayed snapshot. Parse a small option chain, verify contract specifications, calculate a few Greeks and payoff scenarios, and compare two strategies against a simple portfolio and no-trade baseline. Test the math independently before adding conversational AI.

**Proposed evaluation measures:** correctness of pricing and payoff calculations, data freshness, contract mapping accuracy, completeness of risk disclosure, and whether decisions are reproducible. No trading performance is claimed.

## The problem behind the product

A broker screen can show prices and positions; a textbook can explain an option's payoff. Neither necessarily answers a **portfolio-specific decision question** with consistent assumptions: *What risk am I taking, how does this contract change my current portfolio, and what conditions would make the trade idea invalid?*

The product thesis is not “AI picks the best option every morning.” It is **a disciplined personal research and risk-review workflow that compares possible actions, including no trade**. Its first goal is better understanding and fewer avoidable errors; any improvement in realized returns would require a much longer, controlled evaluation and cannot be assumed.

### Decisions, user needs, and alternatives

| Current approach | Useful for | Gap to investigate |
| --- | --- | --- |
| Exchange / broker option chains | Current contracts and prices | Harder to connect multiple views with a consistent risk thesis |
| Brokerage portfolio screens | Holdings, orders and P&L | Scenario impacts across positions and model assumptions may be limited |
| Spreadsheets and notebooks | Transparent calculations | Manual updating, contract mapping and reconciliation |
| Educational resources | Concept learning | Not tied to one's actual positions, time horizon or constraints |

**Primary user:** me, learning and researching Indian derivatives. No commercial ICP or validated user research is claimed.

## A decision memo, not a trading signal

A high-quality response to “What should I consider today?” would include:

1. **As-of time and data state:** exchange session, last available quote, contract specifications, liquidity and feed limitations.
2. **Portfolio baseline:** open positions, available capital, existing risk and max tolerated loss supplied by the user.
3. **Thesis and evidence:** what observation motivates the idea and what alternative explanations exist.
4. **Eligible strategies:** only contracts that meet predetermined liquidity, defined-risk and data-quality constraints.
5. **Comparable scenarios:** underlying moves, volatility moves, decay, costs and stress events.
6. **Rejection rules:** missing quotes, unstable inputs, concentration, inadequate liquidity, risk-budget breach or no persuasive advantage over no trade.
7. **Human decision and journal:** the analysis and uncertainty, with no automated orders.

**An example should never imply that a chosen strategy is objectively optimal.** Candidate ranking is conditional on a defined objective, scenario assumptions and available evidence. Open interest is positioning information, not a reliable standalone forecast or a precise support/resistance line.

## Quantitative controls and evaluation metrics

| Measure | Definition | Purpose |
| --- | --- | --- |
| Contract integrity | Correct underlying, expiry, option type, strike, multiplier and settlement rules | Prevent invalid instrument comparisons |
| Data freshness | Age of every quote and source, with explicit stale-data rejection thresholds | Avoid presenting old prices as executable |
| Calculation accuracy | Differences against independent reference payoffs, Greeks and portfolio arithmetic | Establish mathematical reliability |
| Risk-limit compliance | Share of proposed candidates meeting user-entered loss, exposure, liquidity and margin limits | Guardrail; unsuitable candidates must be rejected |
| Scenario coverage | Number of material stress dimensions tested (price, IV, time, liquidity/costs) | Reduce fragile one-dimensional views |
| Explainability | Share of conclusions backed by a computation, a sourced observation, or a declared assumption | Detect fabricated or unsupported narratives |
| Research efficiency | Time to reproduce a complete, auditable idea review versus a manual process | Test whether the workbench is useful |
| Decision discipline | Share of examined ideas with documented no-trade analysis and subsequent review | Learn from decisions without cherry-picking wins |

No winning percentage, Sharpe ratio, drawdown reduction or returns improvement is reported: **no real strategy has been validated**. A successful prototype can be a correct *no-trade* conclusion.

### Evaluation gates

- **Gate 1 — Mathematics:** reproduce textbook/independent contract payoffs and Greeks under specified conventions; cover edge cases.
- **Gate 2 — Data:** validate mapping, timestamping, missing quotes, bad spreads, lot size and market-hours handling.
- **Gate 3 — Portfolio:** prove incremental versus standalone exposures and mark-to-market scenario results.
- **Gate 4 — Decision quality:** have a human review at least a small set of recorded cases, including deliberate “no trade” outcomes.
- **Gate 5 — Operational readiness:** only then consider permitted market-data integration; brokerage execution remains outside the current scope.

## Capital-markets boundary and neighboring work

This is a **capital-markets / derivatives research project**, not a stage of Project Matrix's turnaround or business-improvement workflow.

- **Underwriting Engine** is the closest conceptual neighbor: it examines whether an underlying-asset thesis is supported and what could invalidate it. F&O Analyst evaluates **the actual derivatives contract, strategy, and portfolio consequences**. Neither is an implemented prerequisite for the other.
- **API Intelligence** might help vet market-data providers and tools. This is a possible shared practice, not a required integrated platform.
- **Project Matrix** focuses on a company's financial and operational diagnosis, turnaround, and value creation. A company memo could sometimes provide background for investment research, but **no current integration is planned**.

## Boundaries

- This is personal research and education, **not personalized financial advice or a trading signal service**.
- Futures and options can produce rapid losses; some short or leveraged positions can have losses beyond the initial premium or margin.
- Market data can be delayed, incomplete, incorrectly mapped, or restricted by licensing.
- Models are approximations; Greeks and theoretical prices depend on assumptions and can fail under market stress.
- Any future portfolio import requires explicit user consent and secure handling.
- The initial system is **read-only and human-in-the-loop**, with no automated execution.

## Project documents

| Document | Purpose |
| --- | --- |
| [Original concept](docs/concept.md) | Earlier ideas and assumptions |
| [Proposed architecture](docs/architecture.md) | Initial component and data-flow design |
| [Development roadmap](docs/roadmap.md) | Potential milestones and tests |

These documents reflect earlier exploration; this README defines the current research direction.
