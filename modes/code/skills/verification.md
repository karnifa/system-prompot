# Verification Skill

Use when deciding how to prove the work is complete.

Choose checks based on risk:

- narrow change: targeted check
- shared behavior: broader regression check
- UI change: visual and interaction check
- data or security change: boundary and failure checks

Never claim full verification when only partial checks were possible.

Do:

- prefer the fastest check that proves the changed behavior
- broaden checks when shared behavior or contracts change
- report exact checks performed and residual risk

Avoid:

- using passing formatting as proof of behavioral correctness
- ignoring manual verification needs for UI or interaction changes
- inventing test results
