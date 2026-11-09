# F&O Analyst — Proposed Architecture

**Status:** Exploratory sketch. No components are implemented or validated yet.

```text
Data adapters
   ↓
Normalization
   ↓
Analytics
   ↓
Validation
   ↓
Interface
```

## Components and responsibilities

| Component | Proposed role |
| --- | --- |
| Data adapters | Exchange/broker/vendor inputs with provenance, entitlements and timestamps |
| Normalization | Underlying, expiry, strike, side, lot size, timestamp and contract identity |
| Analytics | OI, change, IV, Greeks, basis, payoffs and position aggregation |
| Validation | Reference calculations, stale-data checks, missing quotes, market-hours awareness |
| Interface | Tables/charts and question-answering that cites the computed metric and assumptions |

## Design principles

- Make every assumption visible and revisit it after real user discovery.
- Keep deterministic calculations and policy checks distinct from AI-generated explanations.
- Track data provenance, timestamps, source limitations and confidence as applicable.
- Prefer minimal dependencies and local/synthetic tests before live integrations.
- Do not store secrets in code or repository files.

## Decisions still open

- Which data provider or broker can lawfully supply the desired contracts and history?
- Are the use cases end-of-day research, intraday monitoring, or personal position analytics?
- How should missing quotes, illiquid strikes and stale snapshots be handled?
- Which strategy structures are first: single legs, spreads or other defined-risk positions?
