# The IROH Manifesto: Software That Runs Where You Are

> *"Perfection in software is not reached when there is nothing left to add, but when there is nothing left that can break."*

---

## 1. Why Shared Hosting and cPanel Still Matter

In the modern software landscape, the industry has become obsessed with complexity. Simple web applications that serve dozens or hundreds of daily users are routinely architected across distributed cloud containers, serverless event queues, managed databases, and multi-region load balancers. What begins as a modest personal project quickly transforms into a $150/month cloud bill and a relentless maintenance burden.

Meanwhile, millions of individuals, freelancers, small businesses, and non-profits already own and operate traditional **shared hosting accounts** — powered by cPanel, Hostinger, Nginx, or Apache — for a few dollars a month. 

Shared hosting is often dismissed as legacy tech. But with modern **PHP 8.2+**, opcode caching, SQLite, and lightweight single-page application (SPA) frontends like Vue 3, a standard shared server can process requests in milliseconds, handle thousands of daily visits, and run reliably for years with zero server management overhead.

**IROH** (*It Runs On Hostinger*) was founded on a simple realization: **We don't need cloud over-engineering. We need software that runs where people already live.**

---

## 2. Core Architectural & Design Principles

Every project under the IROH initiative is built upon five foundational pillars:

### I. Plain-Text & Open Formats First
Data should outlive software. We prioritize human-readable Markdown files, plain JSON, SQLite files, and standard SQL schemas over opaque proprietary databases. If an application ceases development ten years from now, you must still be able to open your data in any text editor.

### II. Zero Vendor Lock-in
You should never be trapped inside a closed ecosystem or bound to recurring SaaS fees. IROH software is 100% self-hosted, open source, and portable. Moving your data to another provider should be as simple as copying a directory or exporting a `.sql` dump via phpMyAdmin.

### III. Ultra-Low Maintenance Cost
Software shouldn't demand constant updates just to stay alive. By adhering to stable PHP core standards, vanilla web APIs, and backward-compatible SQL engines, IROH applications are built to run peacefully in the background for years without breaking due to vendor API deprecations.

### IV. Single-Engineer Understandability
A single developer should be able to clone an IROH project, read through the codebase in an afternoon, understand how every piece fits together, and audit its security without navigating through dozens of abstract microservices.

### V. Pragmatic Multi-Tenancy & Single-Tenant Simplicity
We favor simple, self-contained single-tenant deployments or straightforward workspace isolation models. We build software for individuals, small teams, and independent operators who value sovereignty over hyper-scale multi-cluster complexity.

---

## 3. The "Wise Elder" Metaphor

The initiative takes its name and philosophical attitude from the archetype of the **wise elder** — a quiet, resilient mentor who has experienced the grand, chaotic complexity of the world and ultimately chooses simplicity, patience, and a calm cup of tea.

In software engineering, young architectures often seek validation through complexity: adding layers of abstraction, microservices, and trendy frameworks simply because they exist. The wise elder understands that true sophistication lies in restraint:

* **Patience over hype:** We do not rewrite our codebase for every new framework trend.
* **Resilience over fragility:** A single server script that never crashes is superior to a distributed cluster that breaks on every dependency bump.
* **Warmth over cold abstraction:** Software should be welcoming, accessible, and easy to run — even for a non-technical user uploading a `.zip` file in cPanel.

---

## 4. Legal & Conceptual Disclaimer

The IROH initiative is an independent open-source software project created by `suporterfid`. The name "IROH" serves strictly as an acronym for **"It Runs On Hostinger"** while paying a light, conceptual homage to the wise mentor archetype found in folklore and modern storytelling.

This initiative is **not affiliated with, endorsed by, or associated with** Paramount Global, Nickelodeon, or the creators of *Avatar: The Last Airbender*. No official images, logos, trademarked names, or copyrighted dialogue are used in any IROH software or documentation. All visual assets, logos, and written content in this initiative are original works.
