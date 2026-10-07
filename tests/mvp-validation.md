# MVP validation notes

**Spec:** 0.1.0  
**Scope:** fresh-agent handoff / behavioral dogfood  
**Status:** design-level validation plus one real learner golden-path session; native Japanese review remains pending.

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


## Real learner dogfood — golden path

A first real text-session learner completed the MVP successfully.

Observed evidence:
- zero-setup start worked;
- situational A/B beginner scaffolding worked;
- support reduced into free romaji production;
- learner independently produced the one-person response;
- learner reused the ordering pattern across oolong tea and highball;
- the capstone changed party size and drink;
- no listening evidence was collected because the session was text-based.

The session did **not** exercise wrong answers, hint requests, romaji restoration, remediation, conversational repair, voice behavior, or portable-state re-entry.

### Compliance finding

The runtime generated untrusted staff acknowledgements (`はい` and `はい、かしこまりました`) after successful orders. This was a runtime compliance failure: the existing trusted-content boundary did not authorize those expressions.

Regression coverage is now required by behavioral test B27 and the explicit world-response rule in `AGENTS.md`.

### Scope finding

The previous completion CTA implied that `Read the menu` was immediately available even though Chapter 2 did not exist. Until that content is implemented, the MVP must end honestly as complete and label menu reading as the next planned chapter.

## Targeted retest gate

Before expanding curriculum, exercise at least:
1. wrong party-size answer;
2. explicit help/romaji request;
3. English response to a Japanese prompt;
4. failure after scaffold release and support restoration;
5. voice path when a suitable voice-capable fresh agent is available.

Do not treat unexercised paths as validated merely because they are specified.


## Voice-discoverability dogfood finding

The first learner session occurred in text even though the host experience was voice-capable. This exposed a distinction missing from the original runtime contract:

- **available capability** determines whether voice should be discoverable;
- **active modality** determines how the current interaction should be presented and what evidence can be collected.

The runtime must mention voice once near the beginning when it is available but inactive, without adding a setup gate. If voice is already active, it should simply use voice-first behavior. Behavioral coverage: B29-B30.

## Voice dogfood — observed presentation defect

In an actual voice session, Japanese script followed by romaji was read aloud as two renditions of the same phrase. This is a confirmed presentation failure, not evidence of poor Japanese content. Voice V1 adds spoken/visual surface separation and unified-host fallback; tests B31–B35 cover regressions. These tests are **specified, not yet empirically passed**. A fresh voice session is required before declaring the issue resolved.

## Unified interaction UX implementation

Consolidated two duplicate Japanese-first progression sections into one cross-modal interaction contract. Added explicit state transitions, one-outstanding-action rule, clarification return semantics, staff-driven capstone behavior, and presentation differences for chat/voice. Added behavioral tests B41–B44 and adversarial scenarios. **These are specification changes, not empirical passes.** The next gate is paired fresh chat and voice dogfood, followed by targeted failures and capstone verification.
