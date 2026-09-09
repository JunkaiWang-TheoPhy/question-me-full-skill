---
name: question-me-full
description: Use after an agent has completed a meaningful task or project phase and the user explicitly wants objective questions plus persistent project-level learning records across assessment sessions.
---

# Question Me Full

Test the user's understanding of completed agent work and retain project-level learning records. Unlike pre-execution `grilling`, `question-me-full` grades answers against existing evidence. Answers never authorize project changes. Label possible project errors as candidate corrections and change modes only on explicit request.

Run only when explicitly invoked. On every run, read [the record lifecycle](references/record-lifecycle.md) before creating or updating Question-Me data.

## Prepare

Use the current task plus only explicitly included tasks or artifacts. Inspect its conversation, artifacts, diffs, tests, sources, decisions, corrections, and limitations. Never write Question-Me data into the assessed project.

Build a mastery map that follows both:

- project history: goal, route, implementation, verification, limitations;
- understanding depth: result, mechanism, evidence, changed-condition consequences.

Ask only about user-accessible evidence, not hidden reasoning or incidental trivia. For unresolved claims, “the available evidence cannot determine this” may be correct.

Before showing a batch, write a temporary answer key containing each number, correct choice, short basis, critical evidence, and partial-credit eligibility. It must predate the user's answers.

Before the first batch, give a one-to-three-sentence theme summary in the user's language without revealing answers. Prefer this natural shape: `我们将研究「<主题>」，也就是 <用简明语言说明本轮主要考察什么以及必要的证据边界>。`

## Ask in Batches

Use only single-choice, multiple-choice, and true/false questions. Render every true/false item with this answer block and use the same A/B labels in the answer key and grading:

```text
A. 对
B. 错
```

Ask the current knowledge frontier in one manageable batch; split it when answer mapping becomes unclear. Downstream questions wait for prerequisite coverage.

Follow the project's causal sequence while increasing from result recognition to mechanism, evidence, and changed-condition reasoning. Adapt to the project, explicit preferences, and demonstrated performance.

## Grade and Continue

After the user submits a batch:

1. Grade every item together as correct, partly correct, incorrect, or unsupported by current evidence.
2. For each wrong item, give the correct answer and a concise explanation. For critical items, link the exact source location and identify its commit or uncommitted state.
3. Give no aggregate accuracy yet.
4. In the lower half of the same response, ask the next batch from the newly unlocked frontier.

For multiple-choice partial credit, award the fraction of correct options selected only when every selected option is correct; selecting any incorrect option yields zero.

Revisit errors with low-overlap variants that change at least two of context, reasoning direction, conditions, evidence, or distractors. Revisit load-bearing errors sooner.

## End

End on important-scope coverage, a user stop or “I understand,” or an unrelated topic. For a topic switch, finalize silently, answer the new request, then append one short save notice.

At any ending, congratulate completion without claiming the score proves mastery. Only then report overall and core accuracy at a readable precision, followed by a natural-language account of understanding, errors, untested areas, and useful review. Offer further `question-me-full` topics in chat without saving them as queued work.
