# Contributing to the IROH Initiative

Thank you for your interest in contributing to the **IROH Initiative** (*It Runs On Hostinger*)! 

Whether you are reporting a bug, proposing a new self-hosted project, writing documentation, or submitting a pull request, your help is warmly welcomed.

---

## 🍵 Philosophy of Contribution

Contributing to IROH is guided by the same principles that power our software: **simplicity, clarity, and calm collaboration**.

We value code readability, comprehensive documentation, and zero-dependency solutions over complex abstractions. When writing code or proposing features, ask yourself: *"Does this keep the application simple to run on a basic $3/month shared server?"*

---

## 🐛 Opening Issues and Bug Reports

If you encounter an issue or inconsistency across any IROH repository:

1. **Search Existing Issues**: Check if the problem or feature has already been discussed in the relevant repository.
2. **Be Specific**: Provide your PHP version, web server environment (cPanel, Nginx, Apache), database engine (SQLite or MySQL), and step-by-step instructions to reproduce the issue.
3. **Use the Issue Templates**:
   * For cross-project alignment or inconsistencies, use the [Cross-project inconsistency template](.github/ISSUE_TEMPLATE/cross-project-inconsistency.md).
   * For proposing a new project to join the initiative, use the [Propose new IROH project template](.github/ISSUE_TEMPLATE/propose-new-iroh-project.md).

---

## 🔀 Pull Request Guidelines

1. **Fork & Branch**: Create a feature branch off `main` in your fork (e.g., `feat/markdown-exporter` or `fix/sqlite-pdo-driver`).
2. **Local Environment**: Test your changes in a local environment matching our production constraints (PHP 8.2+, SQLite/MySQL, Nginx/Apache). Docker Compose files are provided in project repos for local testing convenience.
3. **Keep PRs Focused**: Address one specific issue or feature per pull request. Large, multi-purpose PRs are difficult to review and audit.
4. **Update Documentation**: If your pull request introduces new configuration flags, API endpoints, or environment variables, update the corresponding `README.md` or doc files.

---

## 📝 Commit Message Conventions

We follow the **Conventional Commits** specification to ensure clear git history and automated changelog compatibility across all IROH projects:

* `feat:` A new feature for the user or application.
* `fix:` A bug fix.
* `docs:` Documentation changes only.
* `style:` Code style fixes (formatting, missing semi-colons, whitespace).
* `refactor:` Code refactoring without changing user-facing features or fixing bugs.
* `test:` Adding or updating automated tests.
* `chore:` Maintenance tasks, dependency bumps, or build script updates.

### Examples
```text
feat(jotter): add WebDAV bearer token authentication support
fix(grandpasson): resolve SQLite PDO session lock on concurrent requests
docs(manifesto): clarify single-tenant deployment guidelines
chore: initialize IROH meta-repository with docs and project index
```

---

## 💡 Proposing a New Project for IROH

Have an idea for a self-hosted tool that belongs in the IROH initiative? We are always looking for simple, resilient applications that empower users on shared hosting.

### Minimum Architectural Requirements
To qualify as an official IROH project, your application must meet the following criteria:

1. **Shared Hosting Native**: Must run on standard PHP 8.2+ shared hosting (cPanel, Hostinger, Nginx, Apache) without requiring root/SSH access, Docker in production, or proprietary cloud runtimes.
2. **Open Data Formats**: Data must be stored in open, transparent formats (Markdown files, standard JSON, or plain SQL tables) with full user exportability.
3. **Self-Hosted & Independent**: 100% functional out of the box without mandatory SaaS subscriptions or proprietary cloud API keys.
4. **Dual Database Friendly**: Supports SQLite for single-tenant / zero-config setups and MySQL/MariaDB for shared host databases.
5. **Low Maintenance**: Engineered for long-term stability with minimal dependency bloat.

### How to Propose
To submit a proposal, navigate to our meta-repository issues page and open a [Propose New IROH Project issue](.github/ISSUE_TEMPLATE/propose-new-iroh-project.md).

---

## ✅ IROH Compliance Checklist

Before submitting a pull request or proposing a project, verify compliance against this checklist:

- [ ] **Runs on Shared Hosting**: Verified to execute on PHP 8.2+ with PDO (MySQL & SQLite) on standard cPanel/Apache/Nginx.
- [ ] **Simple Deployment**: Can be deployed via simple `.zip` upload, FTP/SFTP/rsync, or basic `composer install`.
- [ ] **Open Data Formats**: All persistent data uses plain text, Markdown, JSON, or standard SQL tables.
- [ ] **Self-Hosted First**: Zero mandatory external SaaS dependencies or proprietary cloud service requirements.
- [ ] **Single-Engineer Legibility**: Codebase is clean, well-documented, and easy for a single developer to audit.
- [ ] **English & Portuguese Docs**: Core documentation includes clear English guides and Portuguese mirror translations.
