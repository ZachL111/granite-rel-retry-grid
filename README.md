# granite-rel-retry-grid

`granite-rel-retry-grid` keeps a focused Solidity implementation around reliability. The project goal is to develop a Solidity command-oriented project for retry scenarios with transition tables, invalid-transition tests, and no network dependency.

## Why It Exists

I want this repository to be useful as a quick reading exercise: fixtures first, implementation second, verifier last.

## Granite Rel Retry Grid Review Notes

For a quick review, compare `budget pressure` with `recovery gap` before reading the middle cases.

## Features

- `fixtures/domain_review.csv` adds cases for budget pressure and failure width.
- `metadata/domain-review.json` records the same cases in structured form.
- `config/review-profile.json` captures the read order and the two review questions.
- `examples/granite-rel-retry-walkthrough.md` walks through the case spread.
- The Solidity code includes a review path for `budget pressure` and `recovery gap`.
- `docs/field-notes.md` explains the strongest and weakest cases.

## Architecture Notes

The implementation keeps the scoring rule plain: reward signal and confidence, preserve slack, penalize drag, then classify the result into a review lane.

The Solidity checks add a pure review lens and Foundry coverage.

## Usage

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File scripts/verify.ps1
```

## Tests

The verifier is intentionally local. It should fail if the fixture score math, lane assignment, or language-specific test drifts.

## Limitations And Roadmap

The repository is intentionally scoped to local checks. I would expand it by adding adversarial fixtures before adding features.
