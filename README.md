# Cyoda Cloud CLI

> ### Cyoda Cloud is coming.
>
> **⭐ Star this repository** to tell us you want Cyoda Cloud built — every star
> is a vote that shapes our prioritisation, and starring is the fastest way to
> say *"I'd use this."*
>
> **📬 [Join the waitlist](https://cyoda.com/cloud)** to get early access when
> the doors open.

This repository will host the command-line client for
[Cyoda Cloud](https://cyoda.com/cloud) — the managed service for running
systems built on [`cyoda-go`](https://github.com/Cyoda/cyoda-go).

## What is Cyoda Cloud?

[`cyoda-go`](https://github.com/Cyoda/cyoda-go) is an Apache-2.0
**entity database** (EDBMS): every entity carries a lifecycle state machine,
full revision history, and transactional integrity — so applications built on
it have an immutable, point-in-time-queryable audit trail *by construction*.

You can build and run a complete system with it **on your own machine, today,
for free** — the engine plus SQLite or Postgres. No cloud required.

Cyoda Cloud provides managed, isolated `cyoda-go` environments behind a
single control-plane API: provisioning, environment lifecycle, credential
brokering for compute nodes, deployment, and per-environment observability.
The data-plane surface is identical to what you run locally — entity models,
workflow configuration, and compute-node code carry over without
modification.

For the engine itself, see the
[`cyoda-go`](https://github.com/Cyoda/cyoda-go) reference
documentation and <https://docs.cyoda.net>.

### Tiers

| Tier | Storage | Intended use |
| --- | --- | --- |
| Local (OSS, free) | SQLite / Postgres | Development |
| Cloud — shared | Isolated Postgres per environment | Team access, integration, early production |
| Cloud — dedicated | Dedicated Postgres | Production with stricter isolation requirements |
| Cloud — enterprise | `cyoda-go-cassandra` (commercial licence) | High-volume production |

Moving between tiers is an infrastructure change; application code and data
models are unaffected.

## What this CLI will do

The CLI is the developer-facing (and AI-agent-facing) client of the Cyoda
Cloud control plane. The planned surface, subject to change while the design
settles:

- `login` — interactive auth (browser or device flow); tokens stored in your
  OS keychain
- `env create / list / status / delete` — environment lifecycle, with
  `--wait` for provisioning to complete
- `member token mint` — credentials that let a compute node on your machine
  or in your CI join your cloud environment
- `rollout` — trigger and watch deployments of your compute nodes
- `logs tail` — your environment's logs, in your terminal

Built agent-first from day one: data as JSON on stdout, progress and errors
on stderr, stable documented exit codes, idempotency keys on every mutating
call, and a non-interactive variant of every flow. If you drive your
development with an AI coding agent, this CLI is designed to be its hands.

## Status

🚧 **Ground-up redesign in progress.** This repository is intentionally a
skeleton while the new Cyoda Cloud control plane takes shape.

An earlier working prototype (built against a previous control-plane API) is
preserved at the branch
[`legacy/manager-cli`](https://github.com/Cyoda/cyoda-cloud-cli/tree/legacy/manager-cli)
and the tag `pre-redesign`.

## Links

- `cyoda-go` (the OSS engine): <https://github.com/Cyoda/cyoda-go>
- Documentation: <https://docs.cyoda.net>
- Cyoda: <https://cyoda.com>
- Waitlist: <https://cyoda.com/cloud>

## Licence

[Apache 2.0](LICENSE)
