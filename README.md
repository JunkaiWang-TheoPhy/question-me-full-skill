<div align="center">

🇺🇸 [English](README.md) | 🇨🇳 [中文](README.zh.md)

<h1>Question Me Full Skill</h1>

![Visibility](https://img.shields.io/badge/visibility-public-brightgreen) ![License](https://img.shields.io/badge/license-Apache--2.0-blue) ![Type](https://img.shields.io/badge/type-Codex%20skill-6f42c1)

<img src="assets/question-me-mastery-bridge.png" alt="A learner crossing a bridge that appears through questions, review, and transfer" width="100%">

</div>

## Introduction

`Question Me Full` turns completed agent work into evidence-grounded batch quizzes with persistent, private learning records. It reconstructs what happened from the conversation and project evidence, tests the user's understanding, and stores only bounded knowledge summaries under the Codex data directory rather than inside the assessed project.

This is different from `grilling`:

- `grilling` works before execution, when unresolved decisions should shape a plan;
- `question-me-full` works after meaningful work exists, when answers can be judged against evidence and retained across assessment sessions.

## Mastery loop

```text
completed work
      ↓
ground-truth mastery map and temporary answer key
      ↓
objective question batch
      ↓
batch grading with evidence-linked corrections
      ↓
private knowledge summary and transient-key cleanup
```

Full questions and answer keys exist only while an assessment is active. On normal completion, a requested stop, an unrelated topic switch, or an unrecoverable interruption, transient material is removed and the skill keeps a dated natural-language summary of coverage, accuracy, strengths, weaknesses, and untested areas.

## Evidence boundary

The skill does not quiz hidden chain-of-thought, incidental implementation trivia, unsupported claims, or information that was never available to the user. If a project contains numerical support but no proof, the quiz must preserve that boundary instead of grading the conjecture as established fact.

Answers do not authorize project changes. When an answer exposes a possible project error, the skill records the candidate correction and waits for an explicit request before switching into investigation or repair.

## Contents

- [SKILL.md](SKILL.md) contains the canonical behavior.
- [agents/openai.yaml](agents/openai.yaml) contains the Codex interface metadata.
- [evals/scenarios.md](evals/scenarios.md) contains behavioral evaluation cases.
- [references/record-lifecycle.md](references/record-lifecycle.md) defines private persistence and cleanup.

## Installation

Install the repository as a Codex skill or copy it into your configured skills directory, then invoke `$question-me-full` when retained project-level learning history is useful. Use the separate ephemeral `$question-me` skill for rapidly changing projects or one-time assessment.

## License

Licensed under the [Apache License 2.0](LICENSE).
