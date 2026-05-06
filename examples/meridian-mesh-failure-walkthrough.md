# Meridian Mesh Failure Forge Walkthrough

I use this file as a small checklist before changing the SQL implementation.

| Case | Focus | Score | Lane |
| --- | --- | ---: | --- |
| baseline | quorum health | 146 | ship |
| stress | lease drift | 213 | ship |
| edge | replica lag | 211 | ship |
| recovery | membership churn | 122 | watch |
| stale | quorum health | 191 | ship |

Start with `stress` and `recovery`. They create the widest contrast in this repository's fixture set, which makes them better review anchors than the middle cases.

The useful comparison is `lease drift` against `membership churn`, not the raw score alone.
