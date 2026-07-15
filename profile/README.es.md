# Physalis Cloud

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Next.js](https://img.shields.io/badge/Next.js-15-black?logo=next.js)](https://nextjs.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-16-4169E1?logo=postgresql&logoColor=white)](https://www.postgresql.org/)
[![Prisma](https://img.shields.io/badge/Prisma-6-2D3748?logo=prisma&logoColor=white)](https://www.prisma.io/)
[![Docker](https://img.shields.io/badge/Docker-ready-2496ED?logo=docker&logoColor=white)](https://www.docker.com/)

[Français](README.md) · [English](README.en.md) · **Español**

---

**Physalis** es un gestor de secretos self-hosted (Next.js · PostgreSQL ·
AES-256-GCM) que centraliza las variables de entorno, claves SSH y credenciales
de varios proyectos en tus propios servidores, sin depender de un servicio
cloud de terceros.

Multiorganización con control de acceso granular, registro de auditoría
completo, autenticación OIDC de GitHub Actions para los despliegues (sin ningún
secreto almacenado en GitHub) y copias de seguridad cifradas con GPG con
warm-standby.

> 🚀 Versión alojada y gestionada: **[physalis.cloud](https://physalis.cloud)**

Este repositorio es el **punto de entrada** del ecosistema Physalis. Reúne y
documenta los distintos componentes del proyecto, cada uno mantenido en su
propio repositorio.

## Componentes

| Repositorio | Descripción |
|-------------|-------------|
| [**physalis**](https://github.com/physalis-cloud/physalis) | Edición self-hosted — el núcleo de la plataforma: vault cifrado, interfaz web, API de despliegue. |
| [**physalis-cli**](https://github.com/physalis-cloud/physalis-cli) | Interfaz de línea de comandos para controlar y administrar Physalis desde la terminal. |
| [**physalis-sdk**](https://github.com/physalis-cloud/physalis-sdk) | SDK para integrar Physalis y consumir tus secretos desde tus propias aplicaciones. |

## Primeros pasos

Según lo que necesites:

- **Alojar Physalis tú mismo** → sigue la guía de instalación en
  [physalis](https://github.com/physalis-cloud/physalis).
- **Automatizar desde la terminal** → instala la
  [CLI](https://github.com/physalis-cloud/physalis-cli).
- **Crear una integración** → usa el
  [SDK](https://github.com/physalis-cloud/physalis-sdk).

## Características principales

- **Centralización cifrada** — secretos almacenados con AES-256-GCM; ilegibles
  incluso con acceso directo a la base de datos.
- **Multiorganización y RBAC** — permisos granulares (organización / proyecto /
  entorno) con roles de lector, editor y propietario.
- **Despliegues sin secretos en GitHub** — autenticación OIDC: el vault verifica
  la firma del token, comprueba `(repo, workflow, branch)` y devuelve el paquete
  de despliegue completo en una sola petición.
- **Trazabilidad** — cada acción (lectura, edición, inicio de sesión,
  despliegue) se registra con actor, IP y marca de tiempo; exportación a CSV.
- **Resiliencia** — copia de seguridad diaria cifrada con GPG en modo pull,
  warm-standby en un VPS secundario, conmutación por error en menos de 20
  minutos.

## Errores y sugerencias

Abre una issue en el repositorio correspondiente, por ejemplo
[physalis/issues](https://github.com/physalis-cloud/physalis/issues).

## Licencia

Distribuido bajo licencia **MIT**. Copyright (c) 2026 Argoweb.
Consulta el archivo [LICENSE](LICENSE) para ver el texto completo.
