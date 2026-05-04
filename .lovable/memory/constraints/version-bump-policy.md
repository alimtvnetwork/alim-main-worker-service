# Memory: Version-Bump Policy

**Category:** constraints
**Created:** 2026-05-04
**Updated:** 2026-05-04

---

## Summary

Every code-base change in this repo bumps the **minor** version of both `package.json` and (when present) `version.json`. Established by user directive 2026-05-04.

## Details

- Rule: any change to source, config, scripts, or specs that ships in a commit increments the minor version (`X.Y.Z` → `X.(Y+1).0`).
- Files touched on each bump:
  - `package.json` — `"version"` field.
  - `version.json` (root, when it exists) — `Version` field per `spec/01-spec-authoring-guide/17-version-schema.md` §4.
- The bump happens in the same commit as the change.
- Exceptions: pure README/cosmetic doc tweaks the user explicitly marks "no bump". Default is always bump.
- This overrides standard semver "minor = features" — the user wants visible churn.

## Related

- `spec/01-spec-authoring-guide/17-version-schema.md`
- `.lovable/cicd-issues/` (future: 06-version-drift-after-package-bump)
