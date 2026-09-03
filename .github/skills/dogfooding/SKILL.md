---
name: dogfooding
description: Use when asked to dogfood, playtest, critically test, or evaluate how fun and engaging the app feels. Exercises the real user flow in the browser and reports evidence-based feedback on delight, friction, pacing, clarity, replayability, and social energy.
user-invocable: true
---

# Critical Dogfooding

Evaluate the product as a real user, not as its author or a QA checklist. The goal is to discover whether the experience is enjoyable, understandable, and worth repeating.

## Playtest Workflow

1. Open the running app in the browser. Reuse the shared page when available.
2. Read the initial screen and capture the first-impression questions:
   - Is the purpose obvious within a few seconds?
   - Is there a compelling reason to start?
   - Does the visual presentation fit the mood and audience?
3. Start the main flow and perform the core action several times.
4. Complete a meaningful milestone, such as a round, level, win condition, or submission.
5. Continue after the milestone and test whether the app supports another meaningful action.
6. Exercise reversible actions, navigation, reset/restart, and any persistence behavior that a normal user would encounter.
7. Check at least one narrow viewport or responsive state when the browser tools support it.
8. Do not edit code unless the user explicitly asks for fixes. This skill is for observation and feedback.

## What To Observe

Focus on the experience, with concrete evidence from the playtest:

- **First impression:** clarity, mood, visual character, and time to first action.
- **Core loop:** whether actions create curiosity, social interaction, discovery, or satisfying progress.
- **Pacing:** whether progress is too slow, too easy, repetitive, or prematurely finished.
- **Feedback:** whether actions have clear state changes and whether milestones feel rewarding.
- **Social energy:** whether the app creates conversation, stories, collaboration, competition, or merely tracks completion.
- **Content quality:** variety, inclusivity, difficulty spread, freshness, and prompts that invite more than yes/no answers.
- **Replayability:** reasons to start another round and meaningful variation between rounds.
- **Friction:** ambiguity, dead ends, stale states, accidental actions, confusing navigation, and accessibility concerns.

## Test Heuristics

Prefer behavioral checks over speculation. Useful probes include:

- Mark and unmark an item to verify that state is reversible.
- Trigger the main success state and then continue interacting.
- Leave and restart to check whether a new session is actually new.
- Refresh or reopen when persistence exists, checking for stale or contradictory UI.
- Try fast repeated actions and boundary cases that a normal enthusiastic user might produce.
- Compare the first round with the second round: note what changes and what remains identical.

## Report Format

Write the result in the user's language. Lead with a blunt overall verdict and a 1-10 fun score. Then include:

1. **What worked:** 2-4 specific observations from the actual playtest.
2. **What reduced fun:** findings ordered by impact, each tied to observed behavior.
3. **Highest-leverage improvements:** no more than five concrete changes, prioritized by expected effect on enjoyment.
4. **Verdict:** explain whether you would play again, invite others, and why.

Separate confirmed observations from hypotheses. Mention important bugs or incoherent states even though this is not a code review. Do not pad the report with generic praise, exhaustive feature requests, or implementation details unless they help explain the user's experience.
