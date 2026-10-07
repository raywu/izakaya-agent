# Multi-turn regression fixtures — first-drink MVP

These are **test scripts, not passed tests**. Run against a fresh agent with only AGENTS.md and the first-drink fixture. Evaluate each *entire sequence*, not isolated turns. Record actual output and PASS/FAIL; do not award a pass merely because the spec contains the rule.

Every fixture uses **Given → learner turns → Require → Forbid**.

## T1 — Text zero beginner
**Given:** text-only, no state, entering with a friend.
**Turns:** Start → with a friend → correct supported party-size choice → freely order a highball.
**Require:** Japanese staff prompt first; romaji and brief English immediately for unfamiliar material; choices when useful; less support after success; natural continuation.
**Forbid:** English-only lead, inaccessible first prompt, forced choice after open production, invented Japanese.

## T2 — Voice zero beginner
**Given:** voice active, unified spoken/display output, no state.
**Turns:** Start → with a friend → learner freezes → tutor models 二人です → learner repeats.
**Require:** staff Japanese spoken once, brief English situational help after new Japanese, fast model on freeze, natural continuation.
**Forbid:** Japanese repeated through romaji, Japanese-only explanation for a stuck beginner, spoken A/B phone menu.

## T3 — Voice availability matrix
**Given:** three independent sessions: (a) text active, voice known available; (b) text active, capability unknown; (c) voice already active.
**Turns:** Start → first scenario choice.
**Require:** (a) one lightweight voice invitation without gating; (b) no ungrounded capability claim; (c) no setup narration.
**Forbid:** mandatory modality questionnaire, repeated invitation, restart on switching.

## T4 — Uncertain Japanese
**Given:** learner is asked to order a highball.
**Turns:** ハイパブです → short clarification → ハイパルお願いします → confirmation/model if ambiguity persists → ハイボールお願いします.
**Require:** ask what was intended before judging uncertain wording, keep highball context, credit only resolved production.
**Forbid:** confident success, invented correction, pronunciation-quality claim, premature evidence update.

## T5 — Technically valid alternative
**Given:** ordering a highball.
**Turns:** ハイボールください → asks why lesson prefers お願いします.
**Require:** acknowledge that ください can be valid here, give concise register/pattern distinction, return to order without falsely failing.
**Forbid:** treating a valid expression as incorrect merely because it differs from target.

## T6 — Clarification side quest
**Given:** staff has asked ご注文はお決まりですか？; learner chose highball.
**Turns:** What does that mean? → explain please → ハイボールお願いします.
**Require:** brief explanation and return to the same pending order with highball still selected.
**Forbid:** changing item, resetting scene, mandatory yes/no clarification checkpoint.

## T7 — Autonomous progression
**Given:** learner responds correctly to party-size question.
**Turns:** 二人です → learner follows seating cue → orders chosen drink.
**Require:** brief consequence and next trusted staff question without learner saying Continue; one pending action at a time.
**Forbid:** dead-end praise, stacked questions, unrelated events.

## T8 — Authenticity boundary
**Given:** learner successfully orders and trusted fixture has no staff acknowledgement.
**Turns:** ハイボールお願いします.
**Require:** English/nonverbal world consequence or next trusted staff utterance.
**Forbid:** はい, かしこまりました, ではこちらへどうぞ, つきだしです, or any untrusted Japanese as improvised staff content.

## T9 — Capstone and completion
**Given:** learner handled first visit with a friend and a highball.
**Turns:** changed visit alone → 一人です → server asks trusted order question → 生ビールお願いします.
**Require:** staff-led Japanese questions, changed variables, short demonstrated-capability summary, clear MVP end.
**Forbid:** English-only ordering drill, unavailable Chapter 2 CTA, untrusted phrases, no completion.

## T10 — Cross-modal parity
**Given:** same scenario choices in independent chat and voice sessions.
**Turns:** friend → 二人です → highball order → alone → 一人です → beer order.
**Require:** same communicative functions, decisions, progression, correction and capstone boundaries; modality-appropriate supports and honest evidence.
**Forbid:** treating text as listening, speech transcription as pronunciation quality, divergent curriculum.

## Recording protocol
For each run record: host, active modality, known capabilities, learner script, actual tutor turns, PASS/FAIL per Require/Forbid, and a concise failure diagnosis (spec conflict / runtime noncompliance / content gap / host limitation). Do not count imagined transcripts as empirical validation.
