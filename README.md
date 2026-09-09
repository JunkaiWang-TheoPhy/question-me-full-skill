<div align="center">

🇺🇸 [English](README.md) | 🇨🇳 [中文](README.zh.md)

<h1>Question Me Skill</h1>

![Visibility](https://img.shields.io/badge/visibility-public-brightgreen) ![License](https://img.shields.io/badge/license-Apache--2.0-blue) ![Type](https://img.shields.io/badge/type-Codex%20skill-6f42c1)

<img src="assets/question-me-mastery-bridge.png" alt="A learner crossing a bridge that appears through questions, review, and transfer" width="100%">

</div>

## Introduction

`Question Me` turns completed agent work into an evidence-grounded mastery loop. After a meaningful task or project phase, the agent reconstructs what happened from the conversation, artifacts, diffs, tests, sources, decisions, and remaining limitations. It then tests whether the user can explain the mechanism, audit the evidence, and transfer the lesson to a nearby problem.

This is different from `grilling`:

- `grilling` works before execution, when unresolved decisions should shape a plan;
- `question-me` works after meaningful work exists, when answers can be judged against evidence.

## Mastery loop

```text
completed work
      ↓
ground-truth mastery map
      ↓
one high-leverage question
      ↓
answer classification and smallest gap
      ↓
hint, retry, delayed review, and transfer
```

The skill does not treat an answer given immediately after a hint as durable mastery. A topic is mastered only when the user can reconstruct the causal chain, distinguish the chosen approach from a plausible alternative, connect claims to evidence, and apply the mechanism to a new case without answer-revealing hints.

## Evidence boundary

The skill does not quiz hidden chain-of-thought, incidental implementation trivia, unsupported claims, or information that was never available to the user. If a project contains numerical support but no proof, the quiz must preserve that boundary instead of grading the conjecture as established fact.

Answers do not authorize project changes. When an answer exposes a possible project error, the skill records the candidate correction and waits for an explicit request before switching into investigation or repair.

## Contents

- [SKILL.md](SKILL.md) contains the canonical behavior.
- [agents/openai.yaml](agents/openai.yaml) contains the Codex interface metadata.
- [evals/scenarios.md](evals/scenarios.md) contains behavioral evaluation cases.

## Installation

Install the repository as a Codex skill or copy it into your configured skills directory, then invoke `$question-me` after completing meaningful work.

## License

Licensed under the [Apache License 2.0](LICENSE).
