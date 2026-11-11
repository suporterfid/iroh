# IROH Initiative — Technical Project Index

This document serves as the comprehensive technical directory and integration guide for all software projects within the **IROH Initiative** (*suporterfid/iroh*).

---

## Ecosystem Architecture Overview

The IROH ecosystem is designed as a suite of modular, independent, self-hosted web applications that run natively on standard shared hosting environments (Hostinger, cPanel, Nginx, Apache). 

While each project can operate completely standalone, they are engineered to seamlessly interoperate through shared standards:
* **Central Authentication**: Projects delegate single sign-on (SSOn) identity management to **grandpasson**.
* **Open Data Interoperability**: Knowledge, tasks, logs, and documents share a Markdown-first philosophy, utilizing **ConvertDocToMd-PHP** for document ingestion and **jotter** for central knowledge storage.
* **Shared Hosting Infrastructure**: All backend services leverage PHP 8.2+ with PDO database drivers (SQLite for zero-config single-tenant installs and MySQL/MariaDB for shared host databases).

```
                      +-------------------+
                      |   grandpasson     |
                      | (SSO Auth Server) |
                      +---------+---------+
                                | (OAuth2 / Identity)
         +----------------------+----------------------+
         |                      |                      |
         v                      v                      v
+------------------+   +------------------+   +------------------+
|      jotter      |   |   taskconnect    |   |  statusconnect   |
| (Knowledge Base) |   |  (Task Manager)  |   | (Uptime Monitor) |
+--------+---------+   +------------------+   +------------------+
         ^
         | (Doc Conversion)
+--------+---------+                          +------------------+
| ConvertDocToMd-  |                          |    tallymark     |
|       PHP        |                          | (Tally Counter)  |
+------------------+                          +------------------+
```

---

## 🐳 Standard Containerized DX, Testing & Building (Windows & Linux Symmetry)

Every fullstack web project within the IROH initiative is **100% testable, buildable, and runnable locally via Docker Compose** with total symmetry across **Windows (PowerShell)** and **Linux (Bash)** environments.

### Standard `docker-compose.yml` Services
1. `web` — Nginx reverse proxy serving frontend static builds and PHP-FPM API endpoints.
2. `php` — PHP 8.2-FPM container equipped with `pdo_sqlite` and `pdo_mysql`.
3. `frontend` — Node 20 / Vite dev server with Hot Module Replacement (HMR).
4. `db` — MySQL 8.0 server (mirroring Hostinger production database behavior).

### Symmetrical Developer Commands

| Workflow Step | Windows (PowerShell) | Linux (Bash) |
| :--- | :--- | :--- |
| **Start Environment** | `docker compose up -d` | `docker compose up -d` |
| **Run Unit / Integration Tests** | `docker compose exec php ./vendor/bin/phpunit` | `docker compose exec php ./vendor/bin/phpunit` |
| **Compile Production Frontend Build** | `docker compose exec frontend npm run build` | `docker compose exec frontend npm run build` |
| **Execute Database Migrations** | `docker compose exec php php artisan migrate` | `docker compose exec php php artisan migrate` |
| **Deploy Build to Hostinger** | `powershell ./scripts/deploy-hostinger.ps1` | `bash ./scripts/deploy-hostinger.sh` |

---

## 1. jotter

* **Repository**: [`suporterfid/jotter`](https://github.com/suporterfid/jotter)
* **Status**: `v0 complete`
* **Category**: Self-Hosted Knowledge Management

### Description
`jotter` is a modern, self-hosted Markdown knowledge base designed for individuals and teams seeking private, fast, and structured note-taking. It features multi-workspace management, bi-directional wikilinks (`[[Page Name]]`), WebDAV protocol synchronization for desktop/mobile Markdown editors (Obsidian, Logseq, iA Writer), and an embedded Model Context Protocol (MCP) server for native AI assistant integration.

### Tech Stack & Architecture
* **Backend**: PHP 8.2+ / Laravel framework (optimized for cPanel deployment).
* **Frontend**: Vue 3 (Composition API), Vite, Tailwind CSS / Custom CSS.
* **Database**: MySQL / MariaDB (production) or SQLite (local / lightweight).
* **Sync & Protocols**: WebDAV (Sabre/DAV), Model Context Protocol (MCP) over SSE/HTTP.

### Principal Dependencies
* `laravel/framework` — Core web framework.
* `sabre/dav` — WebDAV server protocol support.
* `league/commonmark` — Extensible Markdown parsing engine.

### Documentation References
* [`AGENTS.md`](https://github.com/suporterfid/jotter/blob/main/AGENTS.md) — Agentic workflows & development guidelines.
* [`CLAUDE.md`](https://github.com/suporterfid/jotter/blob/main/CLAUDE.md) — Developer assistance directives.
* `.kiro/steering/` — Architectural steering and domain rules.

### Ecosystem Integration
* **Identity**: Connects to `grandpasson` for single sign-on authentication across workspaces.
* **Ingestion**: Embeds `ConvertDocToMd-PHP` to allow users to import legacy `.doc`, `.docx`, and `.pdf` files directly as native Markdown notes.

---

## 2. grandpasson

* **Repository**: [`suporterfid/grandpasson`](https://github.com/suporterfid/grandpasson)
* **Status**: `In development`
* **Category**: Centralized Single Sign-On (SSO / "SSOn")

### Description
`grandpasson` ("Grandpa's SSO") is a lightweight, zero-cloud Single Sign-On IdentityProvider built specifically to run on shared hosting cPanel accounts. It provides a centralized authentication hub for all IROH projects hosted on a single domain or across subdomains, allowing users to log in once and securely access all their self-hosted applications.

### Tech Stack & Architecture
* **Backend**: Lightweight PHP 8.2+ REST API with PDO.
* **Frontend**: Vue 3 (Composition API), Vite, Responsive CSS.
* **Database**: SQLite (default single-host) or MySQL / MariaDB.
* **Protocols**: OAuth2 / OpenID Connect (OIDC) light implementation & signed JWT session cookies.

### Principal Dependencies
* `firebase/php-jwt` — Secure JSON Web Token encoding/decoding.
* `bramus/router` or lightweight custom router — Fast request routing without heavy framework overhead.

### Documentation References
* [`AGENTS.md`](https://github.com/suporterfid/grandpasson/blob/main/AGENTS.md) — Domain contracts and auth guidelines.
* [`STATUS.md`](https://github.com/suporterfid/grandpasson/blob/main/STATUS.md) — Active feature status and implementation roadmap.

### Ecosystem Integration
* **Central Hub**: Acts as the primary IdentityProvider (IdP) for `jotter`, `taskconnect`, `statusconnect`, and `tallymark`.

---

## 3. taskconnect

* **Repository**: [`suporterfid/taskconnect`](https://github.com/suporterfid/taskconnect) *(also referenced as `suporterfid/a1-task-connect`)*
* **Status**: `In development`
* **Category**: Lightweight Task & Productivity Management

### Description
`taskconnect` is a fast, streamlined task management tool designed for personal focus and small team project tracking. It offers Kanban boards, list views, priority tags, and deadline tracking without the bloat, slow load times, or monthly costs of commercial task SaaS platforms.

### Tech Stack & Architecture
* **Backend**: PHP 8.2+ PDO REST API.
* **Frontend**: Vue 3 (Composition API), Vite, Tailwind CSS.
* **Database**: SQLite or MySQL / MariaDB.

### Principal Dependencies
* `vuedraggable` / `sortablejs` — Smooth drag-and-drop Kanban interface.
* `pinia` — Reactive state management.

### Documentation References
* [`AGENTS.md`](https://github.com/suporterfid/taskconnect/blob/main/AGENTS.md) — Task state management & API contracts.
* [`STATUS.md`](https://github.com/suporterfid/taskconnect/blob/main/STATUS.md) — Current sprint and feature completion status.

### Ecosystem Integration
* **Identity**: Uses `grandpasson` for user login and session management.
* **Notes Integration**: Allows exporting task completion summaries and project logs as Markdown notes into `jotter`.

---

## 4. ConvertDocToMd-PHP

* **Repository**: [`suporterfid/ConvertDocToMd-PHP`](https://github.com/suporterfid/ConvertDocToMd-PHP)
* **Status**: `v0 complete`
* **Category**: Document Processing & Markdown Conversion Utility

### Description
`ConvertDocToMd-PHP` is a pure PHP utility library and CLI tool that converts legacy document formats (`.doc`, `.docx`, and `.pdf`) into clean, standardized Markdown text. It runs entirely on the host server without relying on external cloud conversion APIs, Node.js runtimes, or heavy Java converters.

### Tech Stack & Architecture
* **Runtime**: Plain PHP 8.2+ (CLI and library inclusion).
* **Dependencies**: Standard native PHP extensions (`ext-zip`, `ext-xml`, `ext-mbstring`).

### Principal Dependencies
* Native PHP XML parsing (`SimpleXMLElement` / `XMLReader`) for DOCX parsing.
* Native binary stream processing for legacy formats and PDF text extraction.

### Documentation References
* [`README.md`](https://github.com/suporterfid/ConvertDocToMd-PHP/blob/main/README.md) — Installation, CLI usage, and API usage examples.
* [`STATUS.md`](https://github.com/suporterfid/ConvertDocToMd-PHP/blob/main/STATUS.md) — Conversion fidelity reports and format support matrix.

### Ecosystem Integration
* **Library Integration**: Ingested directly by `jotter` for seamless document-to-note conversion.

---

## 5. statusconnect

* **Service**: [app.statusconnect.net](https://app.statusconnect.net) (hosted; the source repository is private)
* **Status**: `In production`
* **Category**: Uptime Monitoring & Public Status Page

### Description
`statusconnect` is a hosted uptime monitoring service with public status pages. Organizations sign up, add monitors and publish a status page at `/status/{slug}` or on their own domain. It runs on shared hosting: a minute cron claims due monitors from MySQL and checks them in parallel, with no daemon or message broker. A failure is confirmed from a second location before an incident opens. Visitors can follow a page by email or Atom feed. Paid plans are billed through Asaas.

### Tech Stack & Architecture
* **Backend**: Laravel 12 on PHP 8.2+, triggered every minute by the hosting cron.
* **Checks**: HTTP and TCP through `curl_multi`, heartbeat (dead man's switch) pings, and agent metrics pushed by Telegraf or OpenTelemetry.
* **Frontend**: Blade public status pages; Vue 3 / Vite operator app.
* **Database**: MySQL 8.

### Documentation References
* [Public API reference](https://app.statusconnect.net/api) — REST API v1 with `sc_` API keys.

### Ecosystem Integration
* **Identity**: Delegated login through `grandpasson` is supported and off by default; accounts use local email and password.
* **Notifications**: A `taskconnect` notification channel posts incident events to the TaskConnect tasks API, with an idempotency key per incident and event.

---

## 6. tallymark

* **Repository**: [`suporterfid/tallymark`](https://github.com/suporterfid/tallymark)
* **Status**: `Planned`
* **Category**: Minimalist Event & Habit Counter

### Description
`tallymark` is a minimalist counter and logging application for tracking habits, inventory counts, event tallies, and daily metrics. It provides simple increment/decrement interfaces, historical logs, trend visualization, and one-click CSV/JSON export.

### Tech Stack & Architecture
* **Backend**: Light PHP 8.2+ API.
* **Frontend**: Vue 3, Vite, Responsive CSS.
* **Database**: SQLite.

### Principal Dependencies
* `chart.js` — Lightweight visual trend analytics.

### Documentation References
* [`STATUS.md`](https://github.com/suporterfid/tallymark/blob/main/STATUS.md) — Development specification and progress tracker.

### Ecosystem Integration
* **Identity**: Authenticates users via `grandpasson`.
* **Export**: Generates daily Markdown habit logs compatible with `jotter`.
