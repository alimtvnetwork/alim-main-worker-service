# Project Memory

## Core
- 🔴 No swallowed errors. Wrap with `apperror.Wrap()` / `Result<T>` + path/op context.
- 🔴 No nested `if`. Functions ≤ 15 lines. Files < 300. React components < 100.
- 🔴 Booleans: `is`/`has` prefix only. No `!` on calls — use positive guard helpers.
- 🔴 PascalCase for all JSON/DB/log keys. DB tables singular, PK = `{Table}Id` int auto-inc.
- Repo identity: `alimtvnetwork/coding-guidelines-v20`. Never reference `v1` namespaces.
- Memory folder is `.lovable/memory/` (singular). Never create `.lovable/memories/`.
- Single-file convention: `plan.md`, `suggestions.md`, `strictly-avoid.md` carry full history. No per-task folders.
- Bump `package.json` + `version.json` minor version on every code-base change.
- Axios pinned to `1.14.0` / `0.30.3`. `1.14.1` and `0.30.4` are blocked.

## Memories
- [Version-bump policy](mem://constraints/version-bump-policy.md) — Minor bump on every code change; how and where to apply.
- [Lovable folder structure](mem://standards/lovable-folder-structure.md) — Pointer to canonical structure spec; what lives where.
- [Strict-avoid mirror](mem://constraints/strict-avoid-mirror.md) — Pointer to the canonical strictly-avoid quickref.
