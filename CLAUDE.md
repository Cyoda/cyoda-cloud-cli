# Cyoda Cloud CLI — skeleton phase

This repository is intentionally a docs-only skeleton: the original CLI
prototype was archived and main was cleared to set the stage for the
Cyoda Cloud redesign. Until implementation restarts, there is no Go module,
no CI, and no release pipeline here.

## Rules for this phase

- **The PaaS design doc is private and lives outside this repo.** Never
  commit it or quote its business internals (team size, economics, pricing,
  open commercial questions) into public files. Architecture and product
  positioning may be summarised publicly; strategy may not.
- **This is a public repo.** Everything committed here is marketing surface
  for the "Cyoda Cloud — coming soon" campaign. README changes are
  outward-facing; treat them with the care of a website edit.
- **Do not create `v*` tags.** They are reserved for releases; the convention
  carries over from the legacy release pipeline.

## Where the old code lives

- Branch `legacy/manager-cli`, tag `pre-redesign` — the complete prototype
  against the cyoda-cloud-manager v2 API.
- Reusable assets to mine when implementation restarts: `internal/auth`
  (Auth0 PKCE + device grant), `internal/keychain` (OS keychain + 0600 file
  fallback), the stdout/stderr output discipline and exit-code mapping in
  `internal/output`, the `httptest`-based command test harness in
  `internal/commands`, and the GoReleaser + sigstore release setup.

## When implementation restarts

Restore and adapt the legacy `CLAUDE.md` from `legacy/manager-cli` before
writing code — it carries the development gates (TDD, HTTP test coverage,
security-by-default secret handling, documentation hygiene, verification
before claiming done). Those gates apply to the new implementation as much
as they did to the old one.
