# Behavioral acceptance tests

Run these against a fresh capable agent using only `AGENTS.md`, the relevant trusted content, and state when a test supplies it.

Each test uses **Given / When / Require / Forbid**. Differences in prose are fine; differences in core behavior are failures.

## B1 — Zero setup
**Given:** no learner state.  
**When:** learner says `Start`.  
**Require:** begin the izakaya experience immediately; Japanese appears in the opening interaction; provide a safe beginner ramp.  
**Forbid:** asking level, JLPT, kana knowledge, goals, settings, or what to study.

## B2 — Situation, not translation
**Given:** a zero beginner at the party-size exchange.  
**When:** the tutor presents the anchor staff question.  
**Require:** ask what the learner should say/do with appropriate support.  
**Forbid:** routine Japanese-to-English translation as the task.

## B3 — Safe first success
**Given:** first exposure to party-size language.  
**When:** learner is with a friend.  
**Require:** Japanese + romaji and enough context/choices to make action approachable.  
**Forbid:** unaided open production of unseen Japanese.

## B4 — Scaffold release
**Given:** learner succeeds with the fully supported party-size response and later encounters the function again.  
**When:** the context changes.  
**Require:** remove at least one support before the next attempt.  
**Forbid:** repeating the identical fully scaffolded prompt indefinitely.

## B5 — Answer above scaffold
**Given:** choices are shown.  
**When:** learner freely types/says the correct Japanese instead of selecting a choice.  
**Require:** accept it and treat it as stronger production evidence.  
**Forbid:** forcing A/B selection.

## B6 — Item-sensitive romaji
**Given:** learner has handled a familiar expression successfully across multiple encounters while a new expression is introduced.  
**When:** both appear.  
**Require:** familiar material may omit romaji while new material receives it.  
**Forbid:** global romaji on/off behavior.

## B7 — Restore romaji
**Given:** romaji was hidden for familiar text.  
**When:** learner says they cannot read it.  
**Require:** restore romaji for the blocking item immediately.  
**Forbid:** treating this as global regression.

## B8 — Wrong answer
**Given:** learner selects the one-person response while with a friend.  
**When:** tutor evaluates it.  
**Require:** smallest useful correction and retry, then resume the scene.  
**Forbid:** counters lesson, long grammar lecture, or silent acceptance.

## B9 — Understandable but imperfect
**Given:** learner produces understandable but nonpreferred Japanese for a function with a trusted correction.  
**When:** staff could plausibly understand it.  
**Require:** allow communicative success where appropriate, then give a tiny trusted correction.  
**Forbid:** generated \"more natural\" Japanese not present/allowed in trusted content.

## B10 — Remediation stops
**Given:** learner misses, receives support, and still cannot independently produce the target after a brief model.  
**When:** communicative intent is clear.  
**Require:** advance with support and revisit later.  
**Forbid:** endless retry loop.

## B11 — Explicit help
**Given:** learner says `romaji`, `hint`, `choices`, `again`, or equivalent.  
**When:** requested support is available.  
**Require:** give it directly.  
**Forbid:** forcing the learner through an inferred hint ladder first.

## B12 — English answer
**Given:** Japanese staff prompt.  
**When:** learner correctly answers the communicative meaning in English.  
**Require:** credit comprehension/recognition as appropriate, then elicit/model Japanese production.  
**Forbid:** treating English as demonstrated Japanese production.

## B13 — Romaji production
**Given:** beginner responds `futari desu` from memory.  
**When:** the response is appropriate.  
**Require:** accept productive retrieval.  
**Forbid:** requiring Japanese script or upgrading script-reading evidence.

## B14 — No fake listening
**Given:** text-only platform.  
**When:** learner responds correctly to written Japanese.  
**Require:** update reading/recognition/production evidence as appropriate.  
**Forbid:** listening evidence.

## B15 — Audio-first retrieval
**Given:** function is familiar and platform can present audio and delay transcript.  
**When:** tutor retests listening.  
**Require:** audio before transcript; reveal text as rescue if needed.  
**Forbid:** calling simultaneous audio+visible text independent listening.

## B16 — No fake pronunciation grading
**Given:** speech input/transcription but no reliable pronunciation-assessment capability.  
**When:** learner speaks the intended phrase.  
**Require:** accept spoken productive intent when recognized; pronunciation may be modeled.  
**Forbid:** claims such as \"perfect pronunciation.\" 

## B17 — Controlled difficulty
**Given:** learner is succeeding rapidly.  
**When:** tutor increases challenge.  
**Require:** normally change one major dimension at a time.  
**Forbid:** simultaneously removing choices/romaji, changing wording/context, and switching to audio-first.

## B18 — Trusted variation
**Given:** anchor is usable and trusted content includes a recognition variant.  
**When:** tutor tests transfer.  
**Require:** use a trusted variant and connect it to the same communicative function if help is needed.  
**Forbid:** invented variants presented as canonical.

## B19 — Capstone transfer
**Given:** learner reaches chapter frontier.  
**When:** capstone runs.  
**Require:** change at least one meaningful semantic variable; minimize tutoring chrome; rescue remains available.  
**Forbid:** verbatim replay presented as transfer.

## B20 — Evidence-backed summary
**Given:** learner completes chapter with some functions independently and others only with support.  
**When:** tutor says `You can now...`.  
**Require:** claim only demonstrated capabilities.  
**Forbid:** claiming mastery of merely exposed material.

## B21 — Same-chat continuation
**Given:** learner completes a scene or asks a side question.  
**When:** learner says `Continue` or the side question is answered.  
**Require:** resume the exact visit naturally.  
**Forbid:** setup/reset/unnecessary review.

## B22 — New chat with state
**Given:** portable state points to a later frontier.  
**When:** new session begins.  
**Require:** natural re-entry and minimum sufficient recalibration.  
**Forbid:** a fixed review quiz or restarting from zero without evidence.

## B23 — State is a prior
**Given:** state says a function is independent.  
**When:** learner says they forgot or repeatedly struggles.  
**Require:** restore support based on current behavior.  
**Forbid:** arguing with the learner or obeying stale state over behavior.

## B24 — No-state start
**Given:** no state.  
**When:** learner starts.  
**Require:** safe zero-background experience that accelerates if learner demonstrates stronger ability.  
**Forbid:** configuration questionnaire.

## B25 — Missing trusted Japanese
**Given:** continuing would require learner-facing Japanese absent from trusted content.  
**When:** agent needs that expression.  
**Require:** restructure around trusted content or flag it for validation.  
**Forbid:** inventing and promoting it as preferred/canonical teaching content.

## B26 — AGENTS.md self-sufficiency
**Given:** agent has `AGENTS.md`, relevant trusted content, and optional state, but no `docs/`.  
**When:** it teaches the MVP.  
**Require:** correct core behavior.  
**Forbid:** dependence on contributor docs for runtime policy.


## B27 — No untrusted world-response Japanese
**Given:** learner successfully orders a drink and trusted content does not define a staff acknowledgement.  
**When:** the world responds to the successful order.  
**Require:** advance through concise English/nonverbal narration or another explicitly trusted expression.  
**Forbid:** inventing Japanese acknowledgements such as `はい` or `はい、かしこまりました` and presenting them as part of the trusted scene.

## B28 — Honest MVP boundary
**Given:** Chapter 2 trusted content does not exist.  
**When:** the first-drink MVP completes.  
**Require:** clearly mark the MVP complete and describe the next planned chapter as unavailable/planned.  
**Forbid:** an actionable `Continue -> Read the menu` CTA that implies implemented content.
