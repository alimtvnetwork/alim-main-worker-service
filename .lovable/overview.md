# AI Onboarding — Project Overview

**Repo identity:** `alimtvnetwork/coding-guidelines-v20` (do not reference any `v1` namespace).
**Tech stack (this app shell):** React 18 + Vite 5 + TypeScript 5 + Tailwind CSS v3 + shadcn/ui.
**Backend:** None yet — frontend-only per user direction (see `plan.md`).
**Specs are the source of truth:** anything missing from `spec/` does not exist; do not invent rules.

## What this repo is

This repository hosts a large body of **specifications and coding guidelines** under `spec/` (with a consolidated digest at `spec/17-consolidated-guidelines/`) plus a Lovable-built React frontend used as the spec/docs viewer shell. The user is preparing to define a "main service worker" project that will eventually consist of two coordinated sub-projects; specs are pending.

## Key entry points

| Path | What's there |
|------|--------------|
| `.lovable/strictly-avoid.md` | Hard prohibitions — read before any change |
| `.lovable/memory/index.md` | Index of institutional memory |
| `.lovable/plan.md` | Current roadmap |
| `.lovable/cicd-issues/` | CI/CD postmortems — do not repeat these mistakes |
| `.lovable/prompts/01-read-memory.md` | The "read memory" onboarding prompt |
| `spec/17-consolidated-guidelines/` | Self-contained AI digest of every module |
| `spec/01-spec-authoring-guide/` | How specs themselves are structured |
| `version.json` (root) | Canonical repo identity + version (PascalCase keys) |

## AI reading order

1. `.lovable/overview.md` (this file)
2. `.lovable/strictly-avoid.md`
3. `.lovable/user-preferences`
4. `.lovable/memory/index.md`
5. `.lovable/plan.md`
6. `.lovable/suggestions.md`
7. Relevant `spec/17-consolidated-guidelines/*.md` for the task at hand

*Updated: 2026-05-04*
