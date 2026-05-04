# Strictly Avoid — Quick Reference

> Canonical source: `spec/17-consolidated-guidelines/00-strictly-avoid-quickref.md`. This file mirrors the project-critical subset; when in doubt, the canonical file wins.

## 🔴 CODE RED — auto-reject in CI

1. **Never swallow errors.** No empty `catch`, no `_ := fn()`, no floating promises. Wrap with `apperror.Wrap()` / `Result<T>` and include path + operation context.
2. **No nested `if` blocks.** Zero-nesting is absolute. Use guard clauses, named booleans, or extracted helpers.
3. **Functions ≤ 15 lines** (Go ceiling 30). Files < 300 lines. React components < 100 lines.
4. **No `any` in TS / `interface{}` in Go exported APIs / `unwrap()` in Rust prod code.** Use generics or `Result[T]`.
5. **Booleans:** start with `is` / `has` (rarely `should`). Banned prefixes: `can`, `was`, `will`, `not`, `no`, `non`. No `!` on function calls — wrap in a positively named guard.
6. **Max 2 operands per condition.** Never mix `&&` and `||` in one expression — extract sub-expressions.
7. **No `else` after `return` / `throw` / `break` / `continue`.**
8. **No magic strings/numbers** in conditions — named constant or enum.
9. **No bare `true`/`false` positional args** — named constant from a `boolFlags` source.

## Naming & DB

- PascalCase for all JSON/config/log/DB column keys (override JS camelCase).
- Acronyms: `AI`, `DB`, `API`, `URL`, `ID`, `HTTP` — full uppercase.
- DB tables PascalCase **singular**. PK = `{TableName}Id`, integer auto-increment. **No UUID PKs.**
- DB booleans: forbidden prefixes `Not`/`No`. Approved inverses (only): `IsDisabled`, `IsInvalid`, `IsIncomplete`, `IsUnavailable`, `IsUnread`, `IsHidden`, `IsBroken`, `IsLocked`, `IsUnpublished`, `IsUnverified`.
- Entity tables MUST include `Description TEXT NULL`. Transactional/billing tables MUST include `Notes TEXT NULL` + `Comments TEXT NULL`. Both stay nullable.

## Folder & repo structure

- `.lovable/memory/` (singular) — **never** `.lovable/memories/`.
- One file per kind: `plan.md`, `suggestions.md`, `strictly-avoid.md`. **Never** create per-task folders like `completed-tasks/`, `pending-tasks/`, free-form `suggestions/`.
- Never touch `.release/`. Never sync `01-app`, `02-app-issues`, `03-general`, `03-tasks`, `12-consolidated-guidelines` from sibling repos.
- Never hand-edit `version.json` auto fields — run `node scripts/sync-version.mjs`.
- Never hand-edit `src/data/specTree.json` — run the sync script.

## Dependencies

- **Axios:** allowed only at `1.14.0` or `0.30.3`. Versions `1.14.1` and `0.30.4` are blocked.

## Communication

- No filler ("If you have any questions…", "Hope this helps!", "Let me know!").
- No time/timestamp suggestions in or about `readme.txt`.

*Mirror of `spec/17-consolidated-guidelines/00-strictly-avoid-quickref.md` — keep in sync.*
