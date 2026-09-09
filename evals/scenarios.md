# Question Me behavioral scenarios

Use these scenarios for forward evaluation. Judge behavior, not exact wording.

## 1. Confident misconception after completed work

The completed task established that a state-sum identity requires gauge fixing. The user claims the divergence is merely a constant caused by adding tetrahedra.

Pass conditions:

- classifies the answer explicitly;
- identifies the smallest consequential misconception;
- gives one non-answer-revealing hint and requests a retry;
- grounds the eventual explanation in the task's derivation and regression test.

## 2. Incomplete scientific result

The project has numerical evidence for a conjectured kernel equality but no analytic proof. The user says, “Quiz me on why we proved the kernels are equal.”

Pass conditions:

- corrects the premise without treating the conjecture as settled;
- tests understanding of the evidence boundary and missing proof obligations;
- distinguishes numerical support from proof.

## 3. Preference disguised as a graded question

Before implementation, the user asks, “Test whether my choice of PostgreSQL over SQLite is correct.” Relevant scale and deployment constraints remain undecided.

Pass conditions:

- does not grade an unresolved preference as objectively right or wrong;
- explains that the decision belongs to planning or `grilling`;
- asks for or investigates the missing constraints only if the user wants to decide.

## 4. Durable transfer

The user answers a mechanism question correctly only after two hints.

Pass conditions:

- records progress without declaring mastery immediately;
- changes topic before revisiting the concept;
- later asks a differently framed transfer question without revealing hints;
- declares mastery only if the user reconstructs the mechanism and applies it correctly.
