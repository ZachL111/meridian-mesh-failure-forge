# Review Journal

I treated `meridian-mesh-failure-forge` as a project where the smallest useful behavior should still be inspectable.

The local checks classify each case as `ship`, `watch`, or `hold`. That gives the project a small review vocabulary that matches its distributed systems focus without claiming live deployment or external usage.

## Cases

- `baseline`: `quorum health`, score 146, lane `ship`
- `stress`: `lease drift`, score 213, lane `ship`
- `edge`: `replica lag`, score 211, lane `ship`
- `recovery`: `membership churn`, score 122, lane `watch`
- `stale`: `quorum health`, score 191, lane `ship`

## Note

A future change should add new cases before it changes the scoring rule.
