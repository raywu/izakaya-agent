# Critical-path smoke suite

Run against a fresh agent with only `AGENTS.md` and `content/izakaya/first-drink.md`. These are **executable test scripts for a human or external harness**, not proof of passing runs. Capture actual tutor output before evaluating.

## S1 — Japanese staff dialogue cannot become English
**Given:** text beginner, friend, party-size answered.
**Learner:** 二人です。
**Require:** seating cue `こちらへどうぞ。` then trusted ordering question `ご注文はお決まりですか？` before the next order.
**Forbid:** `店員: What would you like to drink?` or any English attributed as staff speech.

## S2 — Beginner English and romaji
**Given:** no Japanese knowledge, text mode, first exposure.
**Learner:** Start → friend.
**Require:** Japanese staff question first, then immediate brief English context and useful romaji/choice support.
**Forbid:** Japanese-only beginner coaching, English-first staff prompt, unsupported unaided production.

## S3 — No duplicate voice audio
**Given:** active unified-output voice host.
**Learner:** Start → friend.
**Require:** each Japanese phrase spoken once, with brief English context after unfamiliar phrases.
**Forbid:** Japanese followed by read-aloud romanization.

## S4 — Automatic progression
**Given:** learner responds correctly to party size.
**Learner:** 二人です.
**Require:** seating recognition beat auto-resolves; next trusted ordering prompt appears without learner typing Continue.
**Forbid:** praise-only dead end or stacked pending learner questions.

## S5 — Uncertain intent
**Given:** learner ordering a highball in voice.
**Learner:** ハイパルお願いします.
**Require:** neutral clarification of intended drink, preserve scene, no evidence upgrade until resolved.
**Forbid:** confidently calling it correct, invented Japanese, pronunciation grading.

## S6 — Authenticity
**Given:** learner successfully orders highball.
**Learner:** ハイボールお願いします.
**Require:** concise English/nonverbal consequence and only trusted subsequent staff language.
**Forbid:** `はい`, `かしこまりました`, `つきだしです`, untrusted taste reaction prompts, or invented events.

## S7 — Staff-led capstone
**Given:** first order completed, changed party size and drink for capstone.
**Learner:** 一人です → 生ビールお願いします.
**Require:** trusted party-size and ordering questions each precede corresponding response.
**Forbid:** English-only ordering drill or skipping the ordering question.

## S8 — Completion
**Given:** capstone final order succeeds.
**Learner:** 生ビールお願いします.
**Require:** evidence-backed summary and explicit MVP complete; menu chapter described as planned, not actionable.
**Forbid:** missing summary or fake Continue CTA.

## Recording and gate
Record for each: date, agent/host, modality, actual turns, pass/fail per criterion, failure classification, and fix commit. Run S1/S2/S4/S5/S6/S7/S8 in text where meaningful; run S2/S3/S4/S5/S6/S7/S8 in voice where meaningful. No simulated example is a pass. A critical-path failure blocks declaring stabilization complete.
