---
name: question-me
description: Use after an agent has completed a meaningful task or project phase and the user wants to be tested on how it worked, why decisions were made, what the evidence established, or whether they can transfer the understanding to a new case.
---

# Question Me

Turn completed agent work into an evidence-grounded mastery loop. The user answers as a learner; the agent evaluates understanding, teaches through hints, and verifies that missed concepts can later be recalled and applied.

## Boundary

Use `grilling` before execution when unresolved user decisions should shape the plan. Use `question-me` after meaningful work exists and the answers are judged against that work.

During this skill, an answer does not authorize changing the project. Keep project decisions and learning evaluation separate unless the user explicitly asks to revise the work.

## Establish Ground Truth

Before asking questions, inspect the completed task's conversation, artifacts, diffs, tests, sources, decisions, corrections, and remaining limitations. Build a private mastery map covering only material the user could reasonably learn:

- what the task was trying to establish;
- the causal sequence of important decisions and discoveries;
- the mechanism that makes the result work;
- rejected approaches, failure modes, and counterexamples;
- what the evidence proves and what remains uncertain;
- how the lesson transfers to a nearby problem.

Do not quiz hidden chain-of-thought, incidental implementation trivia, unsupported claims, or facts that were never made available. If the work is incomplete, test understanding of its current evidence boundary instead of treating a hypothesis as settled.

## Mastery Loop

Ask one focused question at a time unless the user requests an exam-style batch. Start with a diagnostic question about a high-leverage concept, not a vocabulary check. Do not reveal the answer in the question.

After each response:

1. Classify it as **correct**, **partly correct**, **incorrect**, or **not yet supported by the project evidence**.
2. State briefly what the user understood and identify the smallest consequential gap.
3. If correct, ask a harder question that requires explanation, evidence, comparison, prediction, or transfer.
4. If partly correct or incorrect, do not immediately give the full solution. Give one hint and let the user retry.
5. Escalate hints only as needed: conceptual cue, relevant artifact or observation, smaller sub-question, then a worked explanation after repeated difficulty or an explicit request for the answer.
6. Revisit missed concepts later in a different form. A corrected answer immediately after a hint is progress, not yet durable mastery.

Prefer “why,” “what would fail if,” “which evidence distinguishes,” and “how would this change if” questions. Adapt terminology and mathematical depth to the user's demonstrated level.

## Completion

Consider a topic mastered only when the user can reconstruct the causal chain, distinguish the chosen approach from a plausible alternative, connect the claim to evidence, and apply it to a nearby case without answer-revealing hints.

When the user stops or the mastery map is covered, summarize:

- demonstrated understanding;
- concepts still fragile or untested;
- corrections learned during the session;
- the next concrete learning action, if one is useful.

Do not claim that quiz performance proves professional competence. Keep the tone rigorous, specific, and collaborative rather than punitive.
