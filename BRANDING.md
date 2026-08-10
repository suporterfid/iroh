# IROH Initiative — Brand & Visual Guidelines

This document outlines the brand identity, color system, typography, mascot usage rules, voice & tone, and legal guidelines for the **IROH Initiative** (*It Runs On Hostinger*).

---

## 🎨 Color Palette

The IROH color system balances warm parchment tones, rich earth colors, and vibrant accents. It is designed to feel warm, organic, grounded, and legible across both light and dark interfaces.

### Primary Colors

| Color Name | Swatch Description | Hex Code | Usage |
| :--- | :--- | :--- | :--- |
| **Warm Gold** | Amber 500 | `#F59E0B` | Primary highlights, badges, active states |
| **Deep Amber** | Amber 600 | `#D97706` | Brand logos, primary buttons, hero headers |
| **Tea Amber** | Amber 900 | `#78350F` | Dark accents, borders in light mode |

### Secondary & Accent Colors

| Color Name | Swatch Description | Hex Code | Usage |
| :--- | :--- | :--- | :--- |
| **Crimson Red** | Red 800 | `#991B1B` | Secondary branding, destructive alerts, emphasis |
| **Bright Crimson** | Red 700 | `#B91C1C` | Hover states for primary red actions |
| **Jade Green** | Emerald 600 | `#059669` | Success messages, online indicators, positive stats |
| **Bright Jade** | Emerald 500 | `#10B981` | Accent highlights on dark backgrounds |

### Neutral Surfaces

| Color Name | Swatch Description | Hex Code | Usage |
| :--- | :--- | :--- | :--- |
| **Parchment White** | Warm Cream | `#FFFBEB` | Light theme background surface |
| **Parchment Card** | Warm Cream Alt | `#FEF3C7` | Light theme cards, sidebar elements |
| **Charcoal Base** | Dark Gray | `#1F2937` | Primary text color (light mode), dark theme cards |
| **Deep Slate** | Near Black | `#111827` | Dark theme background surface |

---

## 🔤 Typography

IROH pairs classic serif headings with modern, readable UI typefaces and crisp monospace fonts for code and configuration snippets.

### 1. Headings & Logotype: Serif
* **Recommended Fonts**: *Merriweather*, *Lora*, or *Cinzel* (Google Fonts).
* **Usage**: Main application titles, section headers (`h1`, `h2`), project logos, hero banners.
* **Style**: Semi-bold to bold weight, comfortable letter-spacing.

### 2. Body & User Interface: Sans-Serif
* **Recommended Fonts**: *Inter*, *Plus Jakarta Sans*, or system default sans-serif (`system-ui`, `-apple-system`, `BlinkMacSystemFont`).
* **Usage**: Paragraph text, table content, form labels, navigation menus, tooltips.
* **Style**: Regular (400) for body, Medium (500) for labels.

### 3. Code, CLI & Configs: Monospace
* **Recommended Fonts**: *JetBrains Mono*, *Fira Code*, or *Source Code Pro*.
* **Usage**: Code blocks, `.htaccess` snippets, SQL queries, CLI commands, Markdown source views.

---

## 🍵 Mascot Usage Guidelines

The IROH initiative features an official mascot representing the peaceful, resilient, and welcoming nature of the project.

### Asset Locations
* **Local Repository Path**: `assets/branding/iroh-initiative.png`
* **Raw GitHub URL (for cross-repository READMEs)**:
  `https://raw.githubusercontent.com/suporterfid/iroh/main/assets/branding/iroh-initiative.png`

### Markdown Embedding Example
```markdown
![IROH initiative mascot](assets/branding/iroh-initiative.png)
```

### Usage Rules & Recommendations
1. **Contexts of Use**:
   * Top header of repository `README.md` files across all IROH sub-projects.
   * Documentation homepages and initiative landing pages.
   * Welcome screens during application setup / installer wizards.
2. **Sizing & Spacing**:
   * Minimum recommended display height: **120px**.
   * Maintain original aspect ratio without distortion.
   * Provide ample margin around the image (minimum 16px padding).
3. **Backgrounds**:
   * The mascot graphic looks best centered over parchment light backgrounds (`#FFFBEB`) or clean dark slate surfaces (`#1F2937`).
4. **No Unapproved Variations**:
   * Do not generate altered mascot images or modify colors. Use the official file located at `assets/branding/iroh-initiative.png`.

---

## 🗣️ Voice & Tone Guidelines

The voice of IROH is **friendly, wise, calm, and direct**, with light touches of warm "grandpa's cPanel" humor. We explain complex technical concepts simply, without pretentious jargon or artificial urgency.

### Core Principles
* **Be Reassuring**: Software should reduce stress, not create it.
* **Value Simplicity**: Celebrate straightforward solutions like ZIP uploads, single-file databases, and plain-text files.
* **Avoid Jargon**: Prefer "Database connection failed" over "Ephemeral socket handshake timeout".

### Microcopy Examples

#### Error Messages
* ❌ *Generic/Cryptic*: `FATAL: PDOException 1045 Access denied for user 'root'@'localhost'`
* ✅ *IROH Style*: *"Even the best tea spills sometimes. We couldn't connect to your database — please double-check your database user and password in `config.php`."*

#### Fast Onboarding & Welcome Wizards
* ❌ *Corporate/Over-engineered*: `Initializing tenant provisioner pipeline. Deploying container nodes...`
* ✅ *IROH Style*: *"Welcome to your new workspace! Take a deep breath. Your files are safe, your database is configured, and you're ready to get to work."*

#### Tooltips & UI Labels
* ❌ *Complex*: `Executes asynchronous local storage persistence procedure.`
* ✅ *IROH Style*: *"Saves directly to your local database. No cloud sync required."*

---

## ⚖️ Legal & Trademark Directive

* **Original Branding**: The IROH name, logos, and visual assets are original creations belonging to the IROH Initiative (`suporterfid`).
* **Archetype Homage**: The branding is inspired conceptually by the archetype of the wise, peaceful mentor.
* **No Copyright Violation**: **NEVER** use official images, screenshots, copyrighted character dialogue, or logos from *Avatar: The Last Airbender*, Nickelodeon, or Paramount Global in any IROH application, repository, or documentation.
