# meridian-mesh-failure-forge

`meridian-mesh-failure-forge` explores distributed systems with a small SQL codebase and local fixtures. The technical goal is to implement an SQL distributed systems project for failure incremental indexing, using append-only fixtures and checkpoint recovery checks.

## Reason For The Project

The project exists to keep a narrow engineering decision visible and testable. For this repo, that decision is how quorum health and replica lag should influence a review result.

## Meridian Mesh Failure Forge Review Notes

For a quick review, compare `lease drift` with `membership churn` before reading the middle cases.

## What It Does

- `fixtures/domain_review.csv` adds cases for quorum health and lease drift.
- `metadata/domain-review.json` records the same cases in structured form.
- `config/review-profile.json` captures the read order and the two review questions.
- `examples/meridian-mesh-failure-walkthrough.md` walks through the case spread.
- The SQL code includes a review path for `lease drift` and `membership churn`.
- `docs/field-notes.md` explains the strongest and weakest cases.

## How It Is Put Together

The core code exposes a scoring path and the added review layer uses `signal`, `slack`, `drag`, and `confidence`. The domain terms are `quorum health`, `lease drift`, `replica lag`, and `membership churn`.

The SQL checks add a separate view over the domain review fixture.

## Run It

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File scripts/verify.ps1
```

## Check It

The verifier is intentionally local. It should fail if the fixture score math, lane assignment, or language-specific test drifts.

## Boundaries

The fixture set is small enough to audit by hand. The next useful expansion is malformed input coverage, not extra surface area.
