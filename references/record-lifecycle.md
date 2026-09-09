# Question-Me Full record lifecycle

Question-Me Full owns private local learning state under the Codex data directory, never under the assessed project.

## Root and identity

Use `$CODEX_HOME/question-me-full/` when `CODEX_HOME` is configured; otherwise use the client's normal Codex data directory. Prefer the Codex App project ID as the project key. For projectless work, use the task ID. When the user groups several tasks into one logical project, record that mapping explicitly.

```text
question-me-full/
├── profile.md
├── profile.json
└── projects/
    └── <project-id>/
        ├── project.json
        ├── mastery.md
        ├── state.json
        ├── sources.json
        ├── active/
        │   └── <session-id>/
        │       └── answer-key.json
        └── sessions/
            └── <date>-summary.md
```

Create missing directories and files at session start. `project.json` records identity and task associations. `sources.json` records the scoped task and artifact locations, not long-term line-level answer evidence. `state.json` records the active session, coverage, scores, and end state.

## Active state

Keep full questions and the lightweight answer key only under `active/<session-id>/`. Update the key before each batch is shown. It may contain exact evidence links and revision state needed for current grading.

If an active session survives an interruption, resume only when project, task, and question series still match. Otherwise mark it interrupted, finalize a minimal summary, and remove its active material.

## Finalization

Finalize on complete coverage, a user-requested stop, “I understand,” or an unrelated topic switch. On every ending:

1. Write a dated natural-language summary, not a question-by-question table.
2. Record the assessed scope, knowledge-point understanding, overall and core accuracy, stable strengths, weaknesses, untested areas, and ending reason. Keep raw fractional points in structured state, but round displayed percentages sensibly.
3. Do not retain the full questions, correct choices, answer rationales, exact file revisions, or raw user answers by default. Preserve a full answer sheet only when the user explicitly requests it.
4. Remove the active answer key and question material.
5. Update `mastery.md` and structured state.
6. Check the global profile, but write only repeated, stable, or user-confirmed patterns with evidence and confidence.

Do not persist suggested future quiz topics. Suggestions remain in the closing chat response.

## User control

The user may inspect, correct, delete, export, merge, or split project records and global-profile entries. A later correction must revise or remove stale conclusions rather than leaving an append-only negative label.
