# IROH Initiative — Brand & Frontend Visual Identity Specification

This document defines the brand identity, design principles, and framework-agnostic frontend visual specification for all web applications in the **IROH Initiative** (*It Runs On Hostinger*).

It merges the core brand identity of IROH (warmth, resilience, wise elder mascot, cPanel shared hosting focus) with a quiet, content-first, editorially refined frontend visual identity system inspired by modern workspace environments.

---

## 🍵 1. Brand Concept & Philosophy

The **IROH Initiative** combines the calm resilience of the "wise elder" archetype with a modern, content-first workspace visual identity. 

* **Quiet Utility**: Structure, typography, and whitespace do the primary work. Visual chrome recedes so user content and task completion take center stage.
* **Warm Neutral Base**: Off-white and charcoal neutrals reduce glare without tinting or distracting from content.
* **Restrained Color Accent**: Primary brand accents (Warm Gold, Crimson Red, Jade Green) highlight key brand elements, while semantic blue is reserved for primary UI actions and status colors for status communication.
* **Compact Controls, Generous Reading Space**: Compact, reachable UI controls paired with comfortable prose reading measures (720px max-width).
* **Self-Hosted Simplicity**: Built for standard $3/month shared hosting (Hostinger, cPanel, Apache/Nginx, PHP 8.2+).

---

## 🎨 2. Semantic Color Tokens & Brand Palette

Use only semantic CSS variable names in application styles. Component code MUST consume semantic tokens and NEVER literal hex, RGB, or HSL values.

### Brand Accents

| Brand Accent | Hex Code | Intended Usage |
| :--- | :--- | :--- |
| **Warm Gold** | `#F59E0B` / `#D97706` | Brand highlights, logo accents, warm badges |
| **Crimson Red** | `#991B1B` / `#B91C1C` | Secondary brand emphasis, destructive actions |
| **Jade Green** | `#059669` / `#10B981` | Success states, online indicators, positive metrics |

### Semantic Color Token Table

| Token | Light Value | Dark Value | Intended Use |
| :--- | ---: | ---: | :--- |
| `--color-bg-canvas` | `#FFFFFF` | `#191919` | App / main page canvas |
| `--color-bg-surface` | `#F7F6F3` | `#202020` | Secondary surfaces & sidebars |
| `--color-bg-elevated` | `#FFFFFF` | `#252525` | Menus, dialogs, raised cards |
| `--color-bg-hover` | `#EFEDEA` | `#2C2C2C` | Neutral hover fill |
| `--color-bg-selected` | `#E7F0FA` | `#123B60` | Selected row, tab, or nav item |
| `--color-text-primary` | `#252525` | `#F1F1EF` | Primary text (AA 4.5:1 text contrast) |
| `--color-text-secondary` | `#5F5F5F` | `#C6C6C2` | Supporting text & metadata |
| `--color-text-disabled` | `#929292` | `#888884` | Disabled, non-essential text |
| `--color-text-inverse` | `#FFFFFF` | `#191919` | Text on inverse/action fill |
| `--color-text-link` | `#0F5EAB` | `#79B8E8` | Links; visible underline in every state |
| `--color-border-default` | `#D9D7D3` | `#4A4A4A` | Non-essential decorative dividers only |
| `--color-border-strong` | `#8A8882` | `#6E6E6E` | Control boundaries & invalid control outlines |
| `--color-action-primary` | `#1A6DC1` | `#529CCA` | Primary action fill |
| `--color-action-primary-hover` | `#14599E` | `#70B4DE` | Primary action hover fill |
| `--color-action-primary-active` | `#104B86` | `#3E83B5` | Primary action pressed fill |
| `--color-action-primary-content` | `#FFFFFF` | `#111111` | Content on primary action (AA normal text) |
| `--color-action-primary-subtle` | `#E7F0FA` | `#173755` | Quiet primary-action background |
| `--color-focus-ring` | `#1A6DC1` | `#79B8E8` | Focus-visible outer ring (2px offset) |
| `--color-success-fg` | `#126B3A` | `#7CDA9A` | Success text / icon |
| `--color-success-bg` | `#F1FAF4` | `#13291C` | Success background surface |
| `--color-success-border` | `#7CCB98` | `#34794C` | Success border |
| `--color-warning-fg` | `#7A4A00` | `#F5C775` | Warning text / icon |
| `--color-warning-bg` | `#FFF7E6` | `#33250D` | Warning background surface |
| `--color-warning-border` | `#F0B35A` | `#8D6418` | Warning border |
| `--color-danger-fg` | `#B42318` | `#F4A49E` | Danger text / icon |
| `--color-danger-bg` | `#FFF1F0` | `#381B1B` | Danger background surface |
| `--color-danger-border` | `#F29A93` | `#8E4540` | Danger border |
| `--color-info-fg` | `#0F5EAB` | `#9DCCF2` | Informational text / icon |
| `--color-info-bg` | `#EDF5FE` | `#102B45` | Informational background surface |
| `--color-info-border` | `#85BCEB` | `#3D78AA` | Informational border |

### Public CSS Token Contract

All IROH frontend applications MUST define and consume this CSS token structure:

```css
:root,
[data-theme='light'] {
  color-scheme: light;
  --color-bg-canvas: #FFFFFF;
  --color-bg-surface: #F7F6F3;
  --color-bg-elevated: #FFFFFF;
  --color-bg-hover: #EFEDEA;
  --color-bg-selected: #E7F0FA;
  --color-text-primary: #252525;
  --color-text-secondary: #5F5F5F;
  --color-text-disabled: #929292;
  --color-text-inverse: #FFFFFF;
  --color-text-link: #0F5EAB;
  --color-border-default: #D9D7D3;
  --color-border-strong: #8A8882;
  --color-action-primary: #1A6DC1;
  --color-action-primary-hover: #14599E;
  --color-action-primary-active: #104B86;
  --color-action-primary-content: #FFFFFF;
  --color-action-primary-subtle: #E7F0FA;
  --color-focus-ring: #1A6DC1;
  --color-success-fg: #126B3A;
  --color-success-bg: #F1FAF4;
  --color-success-border: #7CCB98;
  --color-warning-fg: #7A4A00;
  --color-warning-bg: #FFF7E6;
  --color-warning-border: #F0B35A;
  --color-danger-fg: #B42318;
  --color-danger-bg: #FFF1F0;
  --color-danger-border: #F29A93;
  --color-info-fg: #0F5EAB;
  --color-info-bg: #EDF5FE;
  --color-info-border: #85BCEB;
}

[data-theme='dark'] {
  color-scheme: dark;
  --color-bg-canvas: #191919;
  --color-bg-surface: #202020;
  --color-bg-elevated: #252525;
  --color-bg-hover: #2C2C2C;
  --color-bg-selected: #123B60;
  --color-text-primary: #F1F1EF;
  --color-text-secondary: #C6C6C2;
  --color-text-disabled: #888884;
  --color-text-inverse: #191919;
  --color-text-link: #79B8E8;
  --color-border-default: #4A4A4A;
  --color-border-strong: #6E6E6E;
  --color-action-primary: #529CCA;
  --color-action-primary-hover: #70B4DE;
  --color-action-primary-active: #3E83B5;
  --color-action-primary-content: #111111;
  --color-action-primary-subtle: #173755;
  --color-focus-ring: #79B8E8;
  --color-success-fg: #7CDA9A;
  --color-success-bg: #13291C;
  --color-success-border: #34794C;
  --color-warning-fg: #F5C775;
  --color-warning-bg: #33250D;
  --color-warning-border: #8D6418;
  --color-danger-fg: #F4A49E;
  --color-danger-bg: #381B1B;
  --color-danger-border: #8E4540;
  --color-info-fg: #9DCCF2;
  --color-info-bg: #102B45;
  --color-info-border: #3D78AA;
}

/* Base Component Binding Examples */
.button--primary {
  background: var(--color-action-primary);
  color: var(--color-action-primary-content);
}
.button--primary:hover {
  background: var(--color-action-primary-hover);
}
.button--primary:active {
  background: var(--color-action-primary-active);
}
.control:focus-visible {
  outline: 2px solid var(--color-focus-ring);
  outline-offset: 2px;
}
.link {
  color: var(--color-text-link);
  text-decoration-line: underline;
  text-decoration-thickness: 1px;
  text-underline-offset: 2px;
}
.link:hover,
.link:focus-visible {
  text-decoration-thickness: 2px;
}
```

---

## 🔤 3. Typography & Font Stacks

All applications load licensed web fonts with `font-display: swap`. System fallbacks MUST preserve readable content while custom fonts load.

```css
--font-ui: Inter, "Noto Sans", "Noto Sans Arabic", "Noto Sans Hebrew", "Noto Sans SC", "Noto Sans TC", "Noto Sans JP", "Noto Sans KR", "Noto Sans Thai", "Noto Sans Devanagari", Arial, sans-serif;
--font-editorial: "Source Serif 4", "Noto Serif", "Noto Naskh Arabic", "Noto Serif Hebrew", "Noto Serif SC", "Noto Serif TC", "Noto Serif JP", "Noto Serif KR", Georgia, serif;
--font-code: "IBM Plex Mono", "Noto Sans Mono", "Noto Sans SC", "Noto Sans TC", "Noto Sans JP", "Noto Sans KR", monospace;
```

### Typography Scale

| Role | Size / Line Height | Font Weight | Usage |
| :--- | ---: | ---: | :--- |
| **Caption / Metadata** | `12px / 16px` | 400 or 500 | Metadata, timestamps, footnote disclosures |
| **UI / Body Compact** | `14px / 20px` | 400 | Compact controls, table cells, sidebar items |
| **Body** | `16px / 24px` | 400 | Primary prose content, articles, descriptions |
| **Section Title** | `20px / 28px` | 600 | Card titles, section headers (`h3`) |
| **Page Subheading** | `24px / 32px` | 600 | Sub-headers (`h2`), modal titles |
| **Page Title** | `32px / 40px` | 700 | Main page headers (`h1`) |
| **Display Title** | `44px / 52px` | 700 | Hero landing page titles |

*Numeric alignment*: Use `font-variant-numeric: tabular-nums` for tables, dates, timers, and aligned numeric columns.

---

## 📐 4. Spatial, Shape, Elevation & Motion Tokens

### Spacing & Touch Targets
* **Spacing Scale**: `0, 4, 8, 12, 16, 20, 24, 32, 40, 48, 64px`
* **Control Horizontal Padding**: `12px` (compact), `16px` (regular)
* **Control Min Height**: `32px` (compact), `40px` (regular)
* **Touch Target Rule**: Every pointer-operable control MUST have a **44x44 CSS px minimum hit target** (via element box or non-overlapping surrounding padding).
* **Radii**: `2px` (inline elements), `4px` (form controls/buttons), `6px` (cards), `8px` (dialogs), `999px` (pills/badges).
* **Border Widths**: `1px` (default separators), `2px` (focus rings & error boundaries).

### Elevation & Shadows

| Level | Shadow CSS Property | Intended Surface |
| :--- | :--- | :--- |
| `--shadow-0` | `none` | Flat inline cards, canvas controls |
| `--shadow-1` | `0 1px 2px rgb(0 0 0 / 0.08)` | Subtle raised cards |
| `--shadow-2` | `0 4px 12px rgb(0 0 0 / 0.14)` | Dropdown menus, popovers |
| `--shadow-3` | `0 12px 28px rgb(0 0 0 / 0.18)` | Modal dialogs & lightboxes |

### Motion & Reduced Motion

* **Color/Opacity Feedback**: `120ms cubic-bezier(0.2, 0, 0, 1)`
* **Control State Changes**: `180ms cubic-bezier(0.2, 0, 0, 1)`
* **Entry / Exit & Expansions**: `240ms cubic-bezier(0.2, 0, 0, 1)` (enter), `cubic-bezier(0.4, 0, 1, 1)` (exit).

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 1ms !important;
    animation-iteration-count: 1 !important;
    scroll-behavior: auto !important;
    transition-duration: 1ms !important;
  }
}
```

---

## 📱 5. Responsive Shell & Layout Architecture

Mobile-first responsive shell with breakpoints at `480px`, `768px`, `1024px`, and `1280px`.

| Viewport Width | Shell Layout Behavior |
| :--- | :--- |
| **`< 480px`** | Single-column canvas; sidebar opens as modal overlay; actions collapse into overflow menu; page padding `16px` + safe-area insets. |
| **`480px – 767px`** | Modal overlay sidebar; primary action visible if space permits; page padding `20px`. |
| **`768px – 1023px`** | Collapsible rail sidebar; persistent top bar; data tables scroll internally within labeled regions. |
| **`1024px – 1279px`** | Persistent collapsible sidebar; full breadcrumbs and action bar; optional two-column layout. |
| **`≥ 1280px`** | Persistent sidebar; wide data views max width `1200px`; prose content max width `720px`. |

### Safe-Area & Measure Constraints
* **Prose Reading Measure**: `max-inline-size: 720px` for comfortable reading.
* **Data View Measure**: `max-inline-size: 1200px` for dense data tables and Kanban views.
* **Reflow Target**: Content MUST reflow down to 320 CSS px (including 400% browser zoom) without loss of content or 2D scrolling.

---

## 🌐 6. Accessibility (WCAG 2.2 AA) & Internationalization (i18n / RTL)

* **Contrast Compliance**: WCAG 2.2 Level AA required. Normal text >= 4.5:1; large text >= 3:1; non-text controls & focus rings >= 3:1.
* **Logical CSS Properties**: Use `margin-inline`, `padding-block`, `inset-inline-start`, `border-inline-start` exclusively for automatic LTR/RTL support.
* **Directional Icon Mirroring**: Mirror directional navigation icons (back/forward arrows, chevrons) in RTL mode. Do NOT mirror non-directional icons (search, close, check, settings, edit, trash, charts, media controls).
* **Focus Order & Keyboard**: All interactive controls are focusable, exhibit `:focus-visible` rings (2px solid `--color-focus-ring`), and support Enter/Space/Arrow key navigation.

---

## 🧩 7. Component State Matrix & UI Microcopy

### Component States
All controls MUST visibly differentiate: `default`, `hover`, `active/pressed`, `focus-visible`, `selected`, `disabled`, and `error/invalid`. Selected states MUST include a non-color cue (e.g. font weight, underline, border, checkmark icon).

### IROH Voice & Tone Microcopy Examples

The voice of IROH is **friendly, wise, calm, and direct**, with light touches of warm "grandpa's cPanel" humor.

* **Error Messages**:
  * ❌ *Cryptic*: `FATAL: PDOException 1045 Access denied for user 'root'@'localhost'`
  * ✅ *IROH Style*: *"Even the best tea spills sometimes. We couldn't connect to your database — please double-check your database user and password in `config.php`."*
* **Onboarding & Setup Wizards**:
  * ❌ *Over-engineered*: `Initializing tenant provisioner pipeline. Deploying container nodes...`
  * ✅ *IROH Style*: *"Welcome to your new workspace! Take a deep breath. Your files are safe, your database is configured, and you're ready to get to work."*
* **Tooltips & Action Labels**:
  * ❌ *Complex*: `Executes asynchronous local storage persistence procedure.`
  * ✅ *IROH Style*: *"Saves directly to your local database. No cloud sync required."*

---

## 🖼️ 8. Mascot Usage Guidelines & Legal Directives

### Official Mascot Asset
* **Local Path**: `assets/branding/iroh-initiative.png`
* **Raw GitHub URL (for cross-repo READMEs)**:
  `https://raw.githubusercontent.com/suporterfid/iroh/main/assets/branding/iroh-initiative.png`

```markdown
![IROH initiative mascot](assets/branding/iroh-initiative.png)
```

### Display Guidelines
* Minimum display height: **120px**.
* Maintain original aspect ratio without stretching or color alteration.
* Position over Warm Parchment (`#FFFBEB` / `#F7F6F3`) or Dark Charcoal (`#191919` / `#202020`) surfaces with ample surrounding margin.

### Legal Directive
* **Original Asset**: The IROH mascot and visual identity are original works belonging to the IROH Initiative (`suporterfid`).
* **No Copyright Infringement**: Do **NOT** use official images, logos, screenshots, or copyrighted quotes from *Avatar: The Last Airbender*, Nickelodeon, or Paramount Global in any IROH software or repository.
