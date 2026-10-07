# Izakaya Agent

Learn practical Japanese by actually navigating an izakaya.

Izakaya Agent is an open specification for turning a capable conversational AI into a lightweight, adaptive Japanese tutor. The learner progresses through a real restaurant visit; vocabulary, reading, listening, speaking, and cultural knowledge appear because they are needed to do the next thing.

**Current MVP:** enter an izakaya, get seated, and order your first drink.

## Start learning

### Copy this into your AI

> Use https://github.com/raywu/izakaya-agent to teach me practical Japanese.
>
> Read AGENTS.md as the canonical tutoring behavior and load the relevant trusted scenario content it directs you to.
>
> Do not summarize the repository or explain the tutoring system.
>
> Begin the learning experience immediately.
>
> Start.

A successful setup should put you into the izakaya within the first interaction. You should **not** need to choose a Japanese level, know kana, or configure a lesson first.

Voice is preferred when the host supports it, especially for staff dialogue and learner responses. Text remains a complete fallback.

### If your AI cannot read the repository correctly

Try the raw instructions:

> Use https://raw.githubusercontent.com/raywu/izakaya-agent/main/AGENTS.md as the canonical instructions for teaching me practical Japanese. Load the relevant trusted scenario content it directs you to. Do not summarize the repository. Begin immediately. Start.

If repository retrieval still fails, open `AGENTS.md`, paste it into the conversation, and ask the agent to follow it as canonical tutoring behavior.

The current spec version is visible at the top of `AGENTS.md`.

## What it should feel like

Not a textbook. Not a translation worksheet. Not a generic role-play bot.

The core experience is:

```text
real-world scene
    ↓
Japanese
    ↓
you act
    ↓
the world responds
    ↓
coaching only when needed
```

For a complete beginner, new Japanese may appear with romaji, context, and choices. Support fades item by item as the learner demonstrates ability and returns when needed.

The learner should increasingly experience **Japanese → action → consequence**.

## Repository

- `AGENTS.md` — canonical runtime tutoring behavior
- `content/` — trusted Japanese and pragmatic constraints for implemented scenarios
- `tests/` — behavioral, adversarial, and authenticity acceptance tests
- `docs/` — contributor rationale; not required by the runtime tutor

## Trusted Japanese

Core learner-facing Japanese is intentionally constrained rather than freely generated. Trusted content records speaker role, recognition/production purpose, context, safe variation, and validation status.

The current MVP fixture is **native-review pending**. Agent review is not presented as native-speaker validation.

## Scope

The MVP covers:

**enter → party size → seating → choose a drink → order it → short transfer capstone**

It does not yet attempt a full izakaya visit, handwritten menus, food ordering, payment, JLPT progression, or pronunciation scoring.

Future chapters should expand the same continuous visit only after the MVP experience is validated.

## Design lineage

The architecture is inspired by [music-theory-agent](https://github.com/raywu/music-theory-agent): tiny learner turns, hidden adaptation, behavioral evidence, repetition with variation, portable state, and `AGENTS.md` as the executable product specification.

Izakaya Agent deliberately replaces question/XP-centered presentation with scene progression: the restaurant moving forward is the reward.

## Contributing

Useful contributions include:

- native-speaker review of trusted Japanese;
- contemporary izakaya usage corrections;
- better recognition variants;
- behavioral/adversarial test cases;
- clearer adaptation rules;
- accessibility and cross-agent compatibility improvements.

When proposing Japanese as a preferred production form or staff recognition target, include enough context to evaluate whether it is natural in that specific interaction.

## License

MIT.
