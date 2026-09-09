# Question Me Full behavioral scenarios

Judge behavior rather than exact wording.

## 1. Explicit batch start

A completed project has a design note, a focused regression test, and a commit. The user explicitly invokes `$question-me-full`.

Pass conditions:

- inspects the scoped evidence and creates Question-Me state outside the project;
- prepares a lightweight answer key before showing questions;
- asks a numbered batch containing only single-choice, multiple-choice, or true/false items;
- precedes the first batch with a brief `我们将研究「…」，也就是…` theme summary that does not leak answers;
- renders every true/false item as `A. 对` and `B. 错`, with A/B used consistently in grading;
- follows the knowledge frontier instead of testing hidden reasoning or trivia.

## 2. Batch grading and continuation

The user submits a mixed batch containing correct, partly correct, and wrong answers.

Pass conditions:

- grades the full batch in the upper half;
- gives correct answers and concise explanations for wrong items;
- gives exact source links and revision state for critical items;
- shows no aggregate accuracy mid-session;
- asks the next frontier batch in the lower half.

## 3. Low-overlap correction

The user misunderstood a load-bearing mechanism.

Pass conditions:

- a later variant changes at least two dimensions of the original item;
- it tests the same knowledge without merely rewording or shuffling choices;
- ordinary errors need not recur immediately.

## 4. Multiple-choice scoring

An item has three correct options. The user selects two correct options and no wrong option, then on another item selects all correct options plus one wrong option.

Pass conditions:

- the first item receives two-thirds credit;
- the second receives zero.

## 5. Incomplete scientific result

The project has numerical support for a conjectured equality but no analytic proof.

Pass conditions:

- permits an evidence-insufficient answer;
- does not turn the conjecture into a settled answer key;
- distinguishes numerical support from proof.

## 6. Passive topic switch

The user starts an unrelated task before the quiz frontier is exhausted.

Pass conditions:

- finalizes the project record outside the project directory;
- removes the temporary answer key and full question material;
- answers the new request without a long interruption;
- appends one short note that the assessment ended and was saved.

## 7. Persistence boundary

The assessment ends normally, on request, or after interruption recovery.

Pass conditions:

- retains a dated natural-language summary of knowledge coverage and response quality, not a question table;
- does not retain correct options, answer rationales, or raw answers by default;
- updates the global profile only for repeated, stable, or user-confirmed patterns;
- lets the user inspect, correct, delete, export, merge, or split records.

## 8. Planning disguised as assessment

Before implementation, the user asks whether an unresolved technology preference is “correct.”

Pass conditions:

- does not grade the preference as an established fact;
- explains that the decision belongs to planning or `grilling`;
- does not treat a quiz answer as authorization to modify the project.
