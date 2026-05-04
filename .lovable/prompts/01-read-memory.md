# Read Memory

> **Purpose:** Mandatory onboarding sequence for any AI assistant joining this project. Saying **"read memory"** in chat refers to this prompt.

> **Rule #0:** Follow every phase sequentially. Do not skip, summarize prematurely, or assume knowledge from training data. The specs are the single source of truth.

---

## Phase 1 — AI Context Layer

Read in this exact order:

| # | File | What you learn |
|---|------|----------------|
| 1 | `.lovable/overview.md` | Project summary, tech stack, navigation |
| 2 | `.lovable/strictly-avoid.md` | Hard prohibitions |
| 3 | `.lovable/user-preferences` | Communication style |
| 4 | `.lovable/memory/index.md` | Institutional knowledge index |
| 5 | `.lovable/plan.md` | Current roadmap |
| 6 | `.lovable/suggestions.md` | Pending ideas |

Then read every file referenced in `.lovable/memory/index.md` and every file in `.lovable/cicd-issues/` (so you don't repeat past CI/CD mistakes).

## Phase 2 — Consolidated Guidelines

Read `spec/17-consolidated-guidelines/00-overview.md`, then files `00-strictly-avoid-quickref.md` and `01-*.md` through `30-*.md` in numeric order. Each is self-contained.

## Phase 3 — Spec Authoring Rules

Read `spec/01-spec-authoring-guide/` in numeric order, including `07-memory-folder-guide.md` and `17-version-schema.md`.

## Phase 4 — Task-Driven Deep Dives

Before any task, read the source spec for that area:

| Task involves… | Read |
|----------------|------|
| Code review/writing | `spec/02-coding-guidelines/` |
| Error handling | `spec/03-error-manage/` |
| Database | `spec/04-database-conventions/` |
| Split-DB | `spec/05-split-db-architecture/` |
| Config | `spec/06-seedable-config-architecture/` |
| Design tokens / theming | `spec/07-design-system/` |
| Docs viewer | `spec/08-docs-viewer-ui/` |
| Code blocks | `spec/09-code-block-system/` |
| PowerShell | `spec/11-powershell-integration/` |
| CI/CD | `spec/12-cicd-pipeline-workflows/` |
| Generic CLI | `spec/13-generic-cli/` |
| Self-update | `spec/14-update/` |
| Distribution & runner | `spec/15-distribution-and-runner/` |
| Generic release | `spec/16-generic-release/` |
| WordPress plugin | `spec/18-wp-plugin-how-to/` |
| App-specific | `spec/21-app/` |
| App issues | `spec/22-app-issues/` |
| App DB | `spec/23-app-db/` |
| App design system | `spec/24-app-ui-design-system/` |

Reading order within each folder: `00-overview.md` → numbered files → `99-consistency-report.md`.

> Note: the prompt's Phase 4 originally cited `spec/12-consolidated-guidelines/`, `spec/13-cicd-pipeline-workflows/`, `spec/15-wp-plugin-how-to/`. Actual folders are `spec/17-consolidated-guidelines/`, `spec/12-cicd-pipeline-workflows/`, `spec/18-wp-plugin-how-to/`. Use the table above.

---

## Anti-Hallucination Contract

1. Never invent rules. Silence in a spec = the rule does not exist.
2. Specs override training data — every time.
3. Cite source: `spec/<file>.md § <section>`.
4. Ask when uncertain. Do not guess.
5. Never merge conventions from other projects/frameworks.
6. No filler closings.

---

## Memory Update Protocol

```
New info?
├─ Institutional knowledge → .lovable/memory/<category>/<name>.md + update memory/index.md
├─ Hard prohibition       → .lovable/strictly-avoid.md (and mirror canonical)
├─ Suggestion (unapproved) → .lovable/suggestions.md
└─ Otherwise              → do not persist
```

- Memory folder: `.lovable/memory/` (singular). Never `memories/`.
- Updating any file: preserve unrelated content. Don't truncate.

---

## Code Change Rule

**Every** change to the codebase bumps the minor version in `package.json` and `version.json` (when present). See `mem://constraints/version-bump-policy.md`.

---

## Completion Confirmation

After Phases 1–3, respond with:

```
✅ Onboarding complete.
- Memory files read: [X]
- Consolidated guidelines read: [Y]
- Spec authoring files read: [Z]

I understand:
- CODE RED rules: [top 3–5]
- Naming conventions: [summary]
- Error handling approach: [one sentence]
- Active plan: [current focus]
- Strict avoidances: [top 3–5]

Ready for tasks.
```

Then stop and wait. Do not propose next steps.

*Prompt v1.0 — saved 2026-05-04.*
