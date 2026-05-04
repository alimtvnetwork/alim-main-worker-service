# Suggestions (pending)

- Add a `version.json` at the repo root in the §4 PascalCase schema (currently only `package.json` carries the version).
- Wire `scripts/sync-version.mjs` + a `pre-commit` hook for `LastCommitSha` automation per `spec/01-spec-authoring-guide/17-version-schema.md` §7.
- Once the user supplies the "main service worker" spec, decide between (a) one repo with two app folders or (b) two repos linked via API.
