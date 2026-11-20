# `agent-ui-ux-skills` — Universal UI/UX Skill Bundle (`AGENTS.md`)

> **Purpose:** This file is the universal entry point for any AI coding agent (OpenCode, Claude Code, OpenAI Codex, Cursor, Windsurf, etc.) working with this repository. When read or imported at session start, the agent must verify that all required UI/UX skills are available in `.agents/skills/` (or the agent's native skills directory), install any missing ones, and follow the routing rules below for all frontend work.

---

## 1. Universal Repository Layout

Use the standard `.agents/skills/` directory so any `agentskills.io`-compatible tool discovers the skills automatically:

```text
agent-ui-ux-skills/
├── AGENTS.md                  # Universal agent instructions & skill router
├── README.md                  # Quick-start & import guide for humans
├── DESIGN.md                  # Starter template for project design tokens
├── PRODUCT.md                 # Starter template for product & audience context
└── .agents/
    └── skills/                # Pre-installed SKILL.md folders (committed to Git)
        ├── frontend-design/
        ├── ui-ux-pro-max/
        ├── impeccable/
        ├── improve-ui/
        └── improve-animations/
```

> **Cross-Agent Compatibility Note:** Most modern agents read `.agents/skills/` and `AGENTS.md` natively. If a specific tool requires its own folder (such as `.claude/skills/` or `.opencode/skills/`), run `npx skills add <path-or-repo> --all` or symlink `.agents/skills/` to that folder.

---

## 2. Core UI/UX Skill Registry

At session start—or during workspace setup—check that each skill below exists in `.agents/skills/`. If missing, install it using the universal `npx skills` CLI:

| Skill ID | Role & Specialty | Universal Install Command | When to Invoke |
| :--- | :--- | :--- | :--- |
| **`frontend-design`** | Visual aesthetics, typography, distinctive layouts, anti-slop direction | `npx skills add https://github.com --skill frontend-design` | Building new pages, components, or visual concepts from scratch. |
| **`ui-ux-pro-max`** | Structured design systems, color palettes, font pairings, UX rules | `npx skills add https://github.com` | Defining or updating `DESIGN.md`, design tokens, and component hierarchies. |
| **`impeccable`** | Active design refactoring, layout polish, and 60+ local anti-slop checks | `npx skills add pbakaus/impeccable` | Iterative styling, refactoring existing UI, or running `/audit` and `/polish`. |
| **`improve-ui`** | Read-only UI surface audit and non-destructive implementation plans | `npx skills add https://github.com --skill improve-ui` | Reviewing existing screens against design evidence before modifying code. |
| **`improve-animations`** | Hardware-accelerated motion, micro-interactions, and transition audits | `npx skills add https://github.com --skill improve-animations` | Adding or auditing CSS/Motion/GSAP transitions and scroll behavior. |

*(To add more skills to `agent-ui-ux-skills`: append a new row to this table with its Skill ID, Install Command, and Trigger Condition, then commit the new skill folder into `.agents/skills/`.)*

---

## 3. Agent Execution & Routing Rules

For any frontend, UI, or UX request, follow this sequence:

1. **Read Project Context First:** Check for `DESIGN.md` and `PRODUCT.md` in the workspace root before writing UI code so colors, spacing, typography, and brand voice stay consistent.
2. **Route by Task Intent:**
   * **New Feature / Page from Scratch:** Use `ui-ux-pro-max` to establish design system rules, then use `frontend-design` to build clean, non-generic interfaces.
   * **Audit / Pre-PR Review (Non-Destructive):** Use `improve-ui` first to generate a read-only critique and implementation plan without modifying files.
   * **Active Refactoring & Polish:** Use `impeccable` (`/audit`, `/polish`, `/normalize`, `/typeset`) to directly clean up spacing, hierarchy, and visual bugs.
   * **Motion & Micro-Interactions:** Use `improve-animations` to ensure transitions are restrained, purposeful, and hardware-accelerated.
3. **Avoid Generic AI Defaults:** Never fall back to unstyled boilerplate, cookie-cutter SaaS hero layouts, or unverified contrast ratios. Enforce WCAG/APCA accessibility and responsive breakpoints on every component.

---

## 4. One-Line Sync Script

Run this command from the `agent-ui-ux-skills` root to install or update every skill in the bundle at once:

```bash
npx skills add https://github.com --skill frontend-design -y && \
npx skills add https://github.com -y && \
npx skills add pbakaus/impeccable -y && \
npx skills add https://github.com --skill improve-ui -y && \
npx skills add https://github.com --skill improve-animations -y
```
