# AGENT REVIEW GUIDE: Aligning Projects with the IROH Initiative

This document serves as the standardized AI Agent prompt and review guide for auditing, updating, and aligning Markdown documentation across any repository (`<PROJECT_NAME>`) belonging to the **IROH Initiative** (*It Runs On Hostinger*).

---

## 🤖 Prompt Template for AI Agents

Copy and execute the prompt below when auditing or standardizing documentation in an IROH sub-project:

```markdown
You are working on the repository `<PROJECT_NAME>`, which is part of the **IROH Initiative** ("It Runs On Hostinger"). 
The central meta-repository and hub for the initiative is:
https://github.com/suporterfid/iroh

### Task Objective
Audit, standardize, and update all Markdown (`.md`) files in this repository to:
1. Adhere strictly to IROH initiative standards (language, tone, architecture, frontend visual identity, and structure).
2. Reference the meta-repository `suporterfid/iroh` as the central source of truth for manifesto, branding, and project index.
3. Align naming conventions, section structures, and cross-project links across the ecosystem.

---

### Central Hub References (DO NOT edit locally; link to meta-repo)
* **IROH Meta-repo**: https://github.com/suporterfid/iroh
* **Manifesto**: https://github.com/suporterfid/iroh/blob/main/MANIFESTO.md
* **Project Index**: https://github.com/suporterfid/iroh/blob/main/PROJECTS.md
* **Branding & Visual Identity Spec**: https://github.com/suporterfid/iroh/blob/main/BRANDING.md
* **Contributing Guide**: https://github.com/suporterfid/iroh/blob/main/CONTRIBUTING.md

---

### Language & Documentation Standards

* **Primary README**: Must be written in **ENGLISH** (`README.md`).
* **Portuguese Mirror README**: Highly recommended / mandatory mirror translation (`README.pt-BR.md`).
* **Language Selector Header**: At the top of BOTH READMEs, include the exact language selector bar:
  * On `README.md`: `🇧🇷 [Leia em Português](README.pt-BR.md) | 🇺🇸 [English](README.md) (this page)`
  * On `README.pt-BR.md`: `🇧🇷 [Leia em Português](README.pt-BR.md) (esta página) | 🇺🇸 [English](README.md)`
* **Supporting Markdown Files**: All secondary files (`STATUS.md`, `BACKLOG.md`, `CHANGELOG.md`, `AGENTS.md`, `CLAUDE.md`, `docs/*.md`) MUST be written in **English**, unless local context specifically requires Brazilian Portuguese (e.g., a region-specific deployment guide).

---

### Specific Audit Tasks for `<PROJECT_NAME>`

#### 1. Inspect Existing Documentation
Read and analyze all existing `.md` files:
* `README.md` (or create if missing)
* `README.pt-BR.md` (or create if missing)
* `STATUS.md`, `BACKLOG.md`, `CHANGELOG.md`, `AGENTS.md`, `CLAUDE.md`, `docs/**/*.md`

#### 2. Standardize `README.md` (English)
Rewrite or adjust `README.md` to contain the following standard structure:
1. **Title & Tagline**: Clear project name and 1-line description.
2. **Overview**: Brief summary (1-2 paragraphs) emphasizing:
   * Self-hosted, lightweight software architecture.
   * Native compatibility with traditional shared hosting (Hostinger, cPanel, Apache/Nginx, PHP 8.2+).
   * How this project fits into the IROH ecosystem.
3. **"Part of the IROH Initiative" Section**:
   * Direct link to the meta-repo: `https://github.com/suporterfid/iroh`.
   * Short explanation of IROH as the central hub for manifesto, branding, and project indexing.
   * Link to `PROJECTS.md` on the meta-repo.
4. **Features**: Bullet points detailing key application features.
5. **Requirements**:
   * Supported PHP runtime (PHP 8.2+ with PDO).
   * Dual database support (SQLite for single-tenant / zero-config; MySQL/MariaDB for shared host cPanel).
   * Explicit note: Docker and Docker Compose are for local development (DX) only — production relies on standard server runtimes.
6. **Frontend & UI Design System** (if project includes a user interface):
   * Highlight compliance with the IROH Notion-inspired, content-first visual identity specification.
   * Mention public CSS semantic tokens contract (`:root`, `[data-theme='light']`, `[data-theme='dark']`).
   * Mention WCAG 2.2 AA contrast compliance and mobile-first responsive shell.
   * Reference `BRANDING.md` on the meta-repo.
7. **Installation**: Step-by-step deployment for shared hosting (ZIP upload / FTP / rsync, `composer install`, `.env` / `config.php`, `.htaccess` URL rewriting).
8. **Usage**: Minimal usage examples or CLI commands.
9. **Authentication / SSO (if applicable)**:
   * Specify if this project integrates with `grandpasson` as its Single Sign-On IdentityProvider (OIDC/OAuth2/signed JWTs).
   * Include direct link to `https://github.com/suporterfid/grandpasson`.
10. **Contributing**: Point to the local `CONTRIBUTING.md` or meta-repo `CONTRIBUTING.md`, noting that initiative-wide governance is coordinated at `suporterfid/iroh`.
11. **License**: Standard MIT license reference.

#### 3. Standardize `README.pt-BR.md` (Portuguese)
* Create or update as a faithful mirror translation of `README.md`.
* Keep the exact same section layout, code blocks, technical names, and links.
* Use the top language selector bar.

#### 4. Consistent Meta-Repo References
Ensure every README includes a dedicated badge or callout box pointing to the main IROH hub:
> 🍵 **Part of the IROH Initiative** (*It Runs On Hostinger*)  
> This project is open-source, self-hosted software built for traditional shared hosting.  
> Learn more at the main hub: [suporterfid/iroh](https://github.com/suporterfid/iroh) | [Manifesto](https://github.com/suporterfid/iroh/blob/main/MANIFESTO.md) | [Projects Index](https://github.com/suporterfid/iroh/blob/main/PROJECTS.md) | [Branding Spec](https://github.com/suporterfid/iroh/blob/main/BRANDING.md)

#### 5. Standardize Supporting `.md` Files
* Ensure `STATUS.md`, `BACKLOG.md`, `CHANGELOG.md`, `AGENTS.md`, and `CLAUDE.md` are in English.
* Standardize header titles ("Status", "Roadmap", "Changelog", "Agent Directives").
* Include a short header notice at the top of each file:
  `> *This project is part of the [IROH Initiative](https://github.com/suporterfid/iroh). See the main hub for manifesto, branding, and ecosystem index.*`

#### 6. Cross-Project Integration Links
Where `<PROJECT_NAME>` integrates with other IROH projects, add an **"Integration with Other IROH Projects"** subsection with direct links:
* `grandpasson` (`suporterfid/grandpasson`) — Central Single Sign-On (SSOn) IdentityProvider.
* `jotter` (`suporterfid/jotter`) — Self-hosted Markdown knowledge base & WebDAV sync.
* `ConvertDocToMd-PHP` (`suporterfid/ConvertDocToMd-PHP`) — Plain PHP DOC/DOCX/PDF to Markdown converter.
* `taskconnect` (`suporterfid/taskconnect`) — Lightweight task & project manager.
* `statusconnect` (`suporterfid/statusconnect`) — Uptime monitoring & public status page.
* `tallymark` (`suporterfid/tallymark`) — Minimalist tally & event counter.

#### 7. Voice & Tone Rules
* **English Voice**: Friendly, direct, technical, with light touches of warm "grandpa's cPanel" humor.
* **Simplicity First**: Praise straightforward solutions like single-file databases, ZIP uploads, and plain-text files.
* **Legal / Trademark Safety**: NEVER use official images, screenshots, logos, or copyrighted quotes from *Avatar: The Last Airbender*, Nickelodeon, or Paramount Global. The branding pays purely conceptual homage to the wise mentor archetype.

#### 8. Safety Constraints
* DO NOT alter application source code or executable files.
* DO NOT change non-documentation directory structures.
* DO NOT replace existing MIT licenses unless visibly invalid.

---

### Completion Criteria & Summary Format

At the end of your execution, output a structured summary of changes made per file:
1. List each updated/created `.md` file with a brief bullet point of modifications.
2. Stage all changed files in git.
3. Prepare a single commit using Conventional Commits format:
   `docs: align <PROJECT_NAME> docs with IROH initiative`
```
