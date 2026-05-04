# CI/CD Issues

This folder records CI/CD postmortems. Each file is a single failure mode + the rule that prevents recurrence. Numeric prefix is stable and append-only.

| # | Title | Status |
|---|-------|--------|
| _none yet_ | — | — |

When a CI/CD failure occurs:
1. Diagnose root cause.
2. Create `NN-<kebab-name>.md` with sections: Symptom · Root Cause · Fix · Prevention.
3. Add to the table above.
4. If it implies a hard prohibition, mirror into `.lovable/strictly-avoid.md`.
