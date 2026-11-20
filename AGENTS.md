# `agent-ui-ux-skills` — Universal UI/UX Design Engineering Bundle (`AGENTS.md`)

> **Purpose:** This file is the universal entry point for any AI coding agent (OpenCode, Claude Code, OpenAI Codex, Cursor, Windsurf, GitHub Copilot, etc.) working with this repository. At session start, verify that all required skills exist in `.agents/skills/` (or the agent's native skills directory), install any missing ones, and follow the **4-Stage Routing Matrix** below to avoid context bloat.

---

## 1. Universal Repository Layout

Use the open `agentskills.io` `.agents/skills/` standard so any compatible coding agent discovers these skills automatically:

```text
agent-ui-ux-skills/
├── AGENTS.md                  # Universal agent instructions & 4-stage task router
├── README.md                  # Documentation & quick-start guide
├── DESIGN.md                  # Project design tokens, color palette & typography
├── PRODUCT.md                 # Target audience, product goals & brand context
└── .agents/
    └── skills/                # Pre-installed SKILL.md folders (committed to Git)
        ├── create-design-md/
        ├── ui-ux-pro-max/
        ├── learn-taste/
        ├── frontend-design/
        ├── shadcn/
        ├── mobile-native/
        ├── impeccable/
        ├── improve-animations/
        ├── improve-ui/
        ├── web-design-guidelines/
        ├── fixing-accessibility/
        └── webapp-testing/
```

> **Cross-Agent Compatibility:** Most modern agents read `.agents/skills/` and `AGENTS.md` natively. If a tool requires its own directory (such as `.opencode/skills/` or `.claude/skills/`), run `npx skills add <path-or-repo> --all` or symlink `.agents/skills/` to that folder.

---

## 2. Complete 12-Skill Registry

At session start—or during workspace setup—verify that each skill below is present in `.agents/skills/`. If missing, install it using the universal `npx skills` CLI:

### Stage 1: Discovery, Design Systems & Taste Persistence

| Skill ID | Specialty & Role | Install Command |
| :--- | :--- | :--- |
| **`create-design-md`** | Scans an existing repo or reference URL to generate evidence-based `DESIGN.md` tokens | `npx skills add https://github.com --skill create-design-md` |
| **`ui-ux-pro-max`** | Generates structured design systems, color palettes, font pairings, and UX rules | `npx skills add https://github.com` |
| **`learn-taste`** | Captures your UI corrections and saves them as permanent rules in `DESIGN.md` | `npx skills add emilkowalski/skills --skill learn-taste` |

### Stage 2: UI Generation & Stack Precision

| Skill ID | Specialty & Role | Install Command |
| :--- | :--- | :--- |
| **`frontend-design`** | Distinctive aesthetics, typography, layout hierarchy, and anti-slop direction | `npx skills add https://github.com --skill frontend-design` |
| **`shadcn`** | Inspects real project aliases, Tailwind setup, and installed components before coding | `npx skills add https://github.com --skill shadcn` |
| **`mobile-native`** | Enforces touch targets, iOS safe areas, `100dvh` viewports, and mobile scroll rules | `npx skills add emilkowalski/skills --skill mobile-native` |

### Stage 3: Refactoring, Polish & Motion

| Skill ID | Specialty & Role | Install Command |
| :--- | :--- | :--- |
| **`impeccable`** | Active design refactoring (`/audit`, `/polish`, `/typeset`, `/bolder`) + 60 anti-slop rules | `npx skills add pbakaus/impeccable` |
| **`improve-animations`** | Hardware-accelerated motion, micro-interactions, and transition audits | `npx skills add https://github.com --skill improve-animations` |

### Stage 4: Auditing, Accessibility & Live Browser QA

| Skill ID | Specialty & Role | Install Command |
| :--- | :--- | :--- |
| **`improve-ui`** | Read-only UI surface auditor that outputs non-destructive implementation plans | `npx skills add https://github.com --skill improve-ui` |
| **`web-design-guidelines`** | Deterministic 100+ rule linter for focus states, forms, hydration shifts, and UX edge cases | `npx skills add vercel-labs/agent-skills --skill web-design-guidelines` |
| **`fixing-accessibility`** | Audits and fixes WCAG compliance, ARIA labels, keyboard traps, and contrast ratios | `npx skills add https://github.com --skill fixing-accessibility` |
| **`webapp-testing`** | Uses Playwright to capture desktop/mobile screenshots and visually verify live UI | `npx skills add https://github.com --skill webapp-testing` |

*(To add more skills: append a new row to the appropriate stage above, add its install line to Section 4, and commit the skill folder into `.agents/skills/`.)*

---

## 3. Agent Execution & Routing Rules

**Context Hygiene Rule:** Never load all 12 skills simultaneously. Read `DESIGN.md` and `PRODUCT.md` first, then load only the 1–2 skills matching the active workflow stage:

1. **Starting a New Project or Extracting Existing Styles:**
   * Load `create-design-md` (if an existing codebase/URL exists) or `ui-ux-pro-max` (for greenfield projects) to populate `DESIGN.md`.
   * Whenever the user gives subjective visual feedback (*"make borders subtler"*, *"tighter padding"*), immediately invoke `learn-taste` to persist the rule in `DESIGN.md`.
2. **Building Pages & Components:**
   * Load `frontend-design` for visual direction.
   * If React/Tailwind/shadcn is detected in `package.json`, load `shadcn`.
   * Always apply `mobile-native` rules for responsive breakpoints, touch targets, and viewport units.
3. **Polishing & Adding Motion:**
   * Use `impeccable` (`/audit`, `/polish`, `/normalize`, `/typeset`) to refine layout rhythm and eliminate AI visual clichés.
   * Use `improve-animations` whenever adding or reviewing CSS/Motion/GSAP transitions.
4. **Pre-PR Review, Accessibility & Visual QA:**
   * For non-destructive review plans, run `improve-ui` first.
   * Run `web-design-guidelines` and `fixing-accessibility` to catch keyboard, ARIA, form, and contrast issues.
   * Run `webapp-testing` (Playwright) to screenshot desktop and mobile viewports and verify rendered output before finishing.

---

## 4. One-Line Sync Script

Run this command from the `agent-ui-ux-skills` root to install or update all 12 skills at once:

```bash
npx skills add https://github.com --skill create-design-md -y && \
npx skills add https://github.com -y && \
npx skills add emilkowalski/skills --skill learn-taste -y && \
npx skills add https://github.com --skill frontend-design -y && \
npx skills add https://github.com --skill shadcn -y && \
npx skills add emilkowalski/skills --skill mobile-native -y && \
npx skills add pbakaus/impeccable -y && \
npx skills add https://github.com --skill improve-animations -y && \
npx skills add https://github.com --skill improve-ui -y && \
npx skills add vercel-labs/agent-skills --skill web-design-guidelines -y && \
npx skills add https://github.com --skill fixing-accessibility -y && \
npx skills add https://github.com --skill webapp-testing -y
```
