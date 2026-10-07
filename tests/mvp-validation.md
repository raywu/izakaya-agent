# MVP validation notes

**Spec:** 0.1.0  
**Scope:** fresh-agent handoff / behavioral dogfood  
**Status:** passes design-level validation; native Japanese review remains pending.

## Fresh-agent smoke test

A fresh agent supplied only with:
- `AGENTS.md`
- `content/izakaya/first-drink.md`
- no learner state

should be able to infer the following without contributor docs:

1. start immediately with a meaningful scene choice;
2. expose Japanese in the opening interaction;
3. scaffold a zero beginner with romaji/context/choices;
4. ask for situational action rather than translation;
5. accept an answer stronger than the offered scaffold;
6. reduce support for familiar functions;
7. move from entry -> party size -> seating -> drink choice -> one ordering pattern;
8. run a varied capstone;
9. claim only demonstrated capabilities;
10. stop at the first-drink MVP boundary.

This is sufficiently specified by `AGENTS.md`; no runtime rule depends on `docs/`.

## Adversarial cases checked

The current spec has explicit behavior for:
- repeated misses;
- explicit help requests;
- English answers;
- romaji production;
- reading/listening asymmetry;
- voice without pronunciation scoring;
- fast learners;
- stale/missing state;
- trusted-content gaps;
- text-only fallback.

## Cross-agent release gate

Before calling the MVP stable, run the behavioral/adversarial suite against at least two fresh capable agents when feasible.

Differences in prose or scene flavor are acceptable.

Treat material differences in these areas as failures requiring specification tightening:
- zero-setup behavior;
- situational vs translation task;
- scaffold release/restoration;
- evidence semantics;
- trusted-content boundaries;
- scenario progression;
- remediation stopping;
- capstone transfer.

## Known external gate

The Japanese fixture is **native-review pending**.

Do not label the MVP's Japanese native-validated or production-ready until a qualified native Japanese reviewer has reviewed the compact fixture according to `tests/authenticity.md`.

## Current conclusion

The repository is ready for real learner dogfood and native-language review.

Do not expand into food ordering, handwritten specials, payment, omakase, or convenience-store content until the first-drink experience has been tested with actual learners and the trusted Japanese fixture has passed native review.
