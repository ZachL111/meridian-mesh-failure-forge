# Field Notes

I would read this project from the data inward: cases first, implementation second.

The domain cases cover `quorum health`, `lease drift`, `replica lag`, and `membership churn`. They sit beside the smaller starter fixture so the project has both a compact scoring check and a domain-flavored review check.

The widest spread is between `lease drift` and `membership churn`, so those are the first two cases I would preserve during a refactor.

The local verifier covers this data so the notes stay tied to code.
