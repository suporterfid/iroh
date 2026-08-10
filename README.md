🇧🇷 [Leia em Português](README.pt-BR.md) | 🇺🇸 [English](README.md) (this page)

# IROH — It Runs On Hostinger

> **Simple, resilient, self-hosted software built for traditional shared hosting.**

![IROH initiative mascot](assets/branding/iroh-initiative.png)

---

## 🍵 Philosophy

The **IROH Initiative** (*It Runs On Hostinger*) is a collection of open-source, self-hosted web applications and utilities engineered specifically to run on standard, low-cost shared hosting environments (such as Hostinger, cPanel, Apache, and Nginx).

In an era of hyper-engineered cloud infrastructure, microservices, and ballooning monthly subscriptions, IROH steps back to value simplicity, calm resilience, and patient independence. We believe that powerful personal and small-team software shouldn't require a Kubernetes cluster or a dedicated DevOps team. If it can run cleanly on a standard $3/month cPanel shared host, it can run anywhere.

Every project in the IROH initiative is crafted around open data formats (such as Markdown files and standard SQL schemas), zero vendor lock-in, and ultra-low maintenance. You own your data, your code, and your host.

---

## 🚀 Initiative Projects

| Project | Description | Tech Stack | Repository | Status |
| :--- | :--- | :--- | :--- | :--- |
| **[jotter](PROJECTS.md#1-jotter)** | Self-hosted Markdown knowledge base with wikilinks, WebDAV sync & MCP server | Laravel, Vue 3, MySQL/SQLite | [`suporterfid/jotter`](https://github.com/suporterfid/jotter) | `v0 complete` |
| **[grandpasson](PROJECTS.md#2-grandpasson)** | Centralized Single Sign-On ("SSOn") IdentityProvider for shared hosting | PHP 8.2+, SQLite/MySQL, Vue 3 | [`suporterfid/grandpasson`](https://github.com/suporterfid/grandpasson) | `In development` |
| **[taskconnect](PROJECTS.md#3-taskconnect)** | Lightweight, fast task manager for personal and team productivity | PHP 8.2+, Vue 3 / Vite, SQLite/MySQL | [`suporterfid/taskconnect`](https://github.com/suporterfid/taskconnect) | `In development` |
| **[ConvertDocToMd-PHP](PROJECTS.md#4-convertdoctomd-php)** | Standalone PHP converter turning DOC, DOCX, and PDF files into Markdown | Plain PHP 8.2+ | [`suporterfid/ConvertDocToMd-PHP`](https://github.com/suporterfid/ConvertDocToMd-PHP) | `v0 complete` |
| **[statusconnect](PROJECTS.md#5-statusconnect)** | Self-hosted status page and uptime monitoring service for shared hosting | PHP 8.2+, Vue 3, SQLite/MySQL | [`suporterfid/statusconnect`](https://github.com/suporterfid/statusconnect) | `Planned` |
| **[tallymark](PROJECTS.md#6-tallymark)** | Minimalist tally counter and habit/event tracking tool | PHP 8.2+, Vue 3 / Vite, SQLite | [`suporterfid/tallymark`](https://github.com/suporterfid/tallymark) | `Planned` |

*For detailed architectural descriptions, integration patterns, and dependency maps, see [PROJECTS.md](PROJECTS.md).*

---

## 🛠️ Common Architectural Requirements

All projects operating under the IROH banner adhere to a shared set of engineering principles:

* **PHP 8.2+ & Dual Database Support**: Powered by modern PHP with PDO support for both SQLite (ideal for single-tenant / zero-config installs) and MySQL/MariaDB (standard on shared host cPanels).
* **No Mandatory Proprietary Cloud Services**: Applications operate 100% self-contained without mandatory SaaS subscriptions, external database dependencies, or proprietary cloud APIs.
* **Local Docker for DX Only**: Docker & Docker Compose are used strictly for local development and automated testing environments. Production execution relies on standard server runtimes.
* **cPanel & Shared Hosting Compatibility**: Deployment is straightforward via standard ZIP upload, FTP/SFTP/rsync, basic `composer install`, and standard `.htaccess` URL rewriting.
* **Open Data Formats**: Data is persisted in human-readable Markdown files or standard SQL structures to guarantee full data portability and auditability.

---

## 📜 Manifesto & Design Standards

Want to learn more about the philosophy behind IROH, the "wise elder" archetype, and our design conventions?

* **[MANIFESTO.md](MANIFESTO.md)** — Read our complete vision on why shared hosting matters and our core design principles.
* **[BRANDING.md](BRANDING.md)** — Explore our visual identity, semantic CSS token contract, frontend design system, typography, and voice & tone guidelines.

---

## 🤝 Contributing

We welcome contributions, project proposals, and feedback from the community!

Please read **[CONTRIBUTING.md](CONTRIBUTING.md)** to learn how to open issues, submit pull requests, adopt commit conventions, or propose new projects to join the IROH initiative.

---

## ⚖️ License

All documentation and specifications in this repository are released under the [MIT License](LICENSE). Individual projects within the IROH initiative maintain their respective MIT licenses in their repositories.
