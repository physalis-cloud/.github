# Physalis Cloud

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Next.js](https://img.shields.io/badge/Next.js-15-black?logo=next.js)](https://nextjs.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-16-4169E1?logo=postgresql&logoColor=white)](https://www.postgresql.org/)
[![Prisma](https://img.shields.io/badge/Prisma-6-2D3748?logo=prisma&logoColor=white)](https://www.prisma.io/)
[![Docker](https://img.shields.io/badge/Docker-ready-2496ED?logo=docker&logoColor=white)](https://www.docker.com/)

[Français](README.md) · **English** · [Español](README.es.md)

---

**Physalis** is a self-hosted secrets manager (Next.js · PostgreSQL ·
AES-256-GCM) that centralizes the environment variables, SSH keys and
credentials of multiple projects on your own servers — with no dependency on a
third-party cloud service.

Multi-organization with granular access control, a full audit log, GitHub
Actions OIDC authentication for deployments (no secrets stored in GitHub), and
GPG-encrypted backups with warm standby.

> 🚀 Hosted and managed version: **[physalis.cloud](https://physalis.cloud)**

This repository is the **entry point** of the Physalis ecosystem. It brings
together and documents the project's components, each maintained in its own
repository.

## Components

| Repository | Description |
|------------|-------------|
| [**physalis**](https://github.com/physalis-cloud/physalis) | Self-hosted edition — the core of the platform: encrypted vault, web UI, deployment API. |
| [**physalis-cli**](https://github.com/physalis-cloud/physalis-cli) | Command-line interface to drive and administer Physalis from the terminal. |
| [**physalis-sdk**](https://github.com/physalis-cloud/physalis-sdk) | SDK to integrate Physalis and consume your secrets from your own applications. |

## Getting started

Depending on what you need:

- **Host Physalis yourself** → follow the installation guide in
  [physalis](https://github.com/physalis-cloud/physalis).
- **Automate from the terminal** → install the
  [CLI](https://github.com/physalis-cloud/physalis-cli).
- **Build an integration** → use the
  [SDK](https://github.com/physalis-cloud/physalis-sdk).

## Key features

- **Encrypted centralization** — secrets stored with AES-256-GCM; unreadable
  even with direct database access.
- **Multi-organization & RBAC** — granular permissions (organization / project /
  environment) with reader, editor and owner roles.
- **Deployments without GitHub secrets** — OIDC authentication: the vault
  verifies the token signature, checks `(repo, workflow, branch)`, and returns
  the full deployment bundle in a single request.
- **Traceability** — every action (read, edit, sign-in, deploy) is recorded with
  actor, IP and timestamp; CSV export.
- **Resilience** — daily GPG-encrypted, pull-based backups, warm standby on a
  secondary VPS, failover in under 20 minutes.

## Bugs & feedback

Open an issue on the relevant repository, e.g.
[physalis/issues](https://github.com/physalis-cloud/physalis/issues).

## License

Released under the **MIT** license. Copyright (c) 2026 Argoweb.
See the [LICENSE](LICENSE) file for the full text.
