# Physalis Cloud

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Next.js](https://img.shields.io/badge/Next.js-15-black?logo=next.js)](https://nextjs.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-16-4169E1?logo=postgresql&logoColor=white)](https://www.postgresql.org/)
[![Prisma](https://img.shields.io/badge/Prisma-6-2D3748?logo=prisma&logoColor=white)](https://www.prisma.io/)
[![Docker](https://img.shields.io/badge/Docker-ready-2496ED?logo=docker&logoColor=white)](https://www.docker.com/)

**Français** · [English](README.en.md) · [Español](README.es.md)

---

**Physalis** est un gestionnaire de secrets self-hosted (Next.js · PostgreSQL ·
AES-256-GCM) qui centralise les variables d'environnement, clés SSH et
credentials de plusieurs projets sur vos propres serveurs — sans dépendre d'un
service cloud tiers.

Multi-organisation avec contrôle d'accès granulaire, audit log complet,
authentification OIDC GitHub Actions pour les déploiements (aucun secret stocké
dans GitHub), et backups chiffrés GPG avec warm-standby.

> 🚀 Version hébergée et gérée : **[physalis.cloud](https://physalis.cloud)**

Ce dépôt est le **point d'entrée** de l'écosystème Physalis. Il regroupe et
documente les différents composants du projet, chacun maintenu dans son propre
dépôt.

## Composants

| Dépôt | Description |
|-------|-------------|
| [**physalis**](https://github.com/physalis-cloud/physalis) | Version auto-hébergée (self-host) — le cœur de la plateforme : vault chiffré, interface web, API de déploiement. |
| [**physalis-cli**](https://github.com/physalis-cloud/physalis-cli) | Interface en ligne de commande pour piloter et administrer Physalis depuis le terminal. |
| [**physalis-sdk**](https://github.com/physalis-cloud/physalis-sdk) | SDK pour intégrer Physalis et consommer vos secrets dans vos propres applications. |

## Démarrage rapide

Selon votre besoin :

- **Héberger Physalis vous-même** → suivez le guide d'installation dans
  [physalis](https://github.com/physalis-cloud/physalis).
- **Automatiser depuis le terminal** → installez la
  [CLI](https://github.com/physalis-cloud/physalis-cli).
- **Construire une intégration** → utilisez le
  [SDK](https://github.com/physalis-cloud/physalis-sdk).

## Fonctionnalités clés

- **Centralisation chiffrée** — secrets stockés en AES-256-GCM ; illisibles même
  avec un accès direct à la base de données.
- **Multi-organisation & RBAC** — droits granulaires (organisation / projet /
  environnement) avec rôles lecteur, éditeur, propriétaire.
- **Déploiements sans secret GitHub** — authentification OIDC : le vault vérifie
  la signature du token, contrôle `(repo, workflow, branch)` et retourne le
  bundle de déploiement complet en une requête.
- **Traçabilité** — chaque action (lecture, modification, connexion,
  déploiement) est enregistrée avec acteur, IP et horodatage ; export CSV.
- **Résilience** — backup quotidien chiffré GPG en pull-based, warm-standby sur
  VPS secondaire, basculement en moins de 20 minutes.

## Bugs & feedback

Ouvrez une issue sur le dépôt concerné, par exemple
[physalis/issues](https://github.com/physalis-cloud/physalis/issues).

## Licence

Distribué sous licence **MIT**. Copyright (c) 2026 Argoweb.
Voir le fichier [LICENSE](LICENSE) pour le texte complet.
