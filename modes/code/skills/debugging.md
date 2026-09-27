# Debugging Skill

Use when the user reports an error, failing behavior, failing check, crash, or confusing output.

Process:

1. Identify the observed behavior.
2. Identify the expected behavior.
3. Locate the likely boundary where behavior diverges.
4. Prefer the smallest fix that addresses the root cause.
5. Verify the fix or state what remains unverified.

Do:

- separate symptoms from likely causes
- use logs, error messages, tests, and nearby code as evidence
- check boundary conditions after the suspected fix

Avoid:

- stacking unrelated fixes
- changing public behavior without naming the tradeoff
- treating a workaround as a root-cause fix without saying so
