# `agent-ui-ux-skills`

A complete, universal UI/UX design engineering skill pack and 4-stage routing system (`AGENTS.md`) for AI coding agents. Import this repository once to give your agent end-to-end design capabilities: token extraction, anti-slop aesthetics, component awareness, mobile-native polish, WCAG accessibility auditing, and live Playwright screenshot verification.

Compatible with **OpenCode**, **Claude Code**, **OpenAI Codex CLI**, **Cursor**, **Windsurf**, **GitHub Copilot**, and any [`agentskills.io`](https://agentskills.io)-compliant coding agent.

---

## What's Inside (12 Curated Skills)

The bundle is structured into **4 progressive workflow stages** so your coding agent only loads the exact skills needed for the current task without wasting context tokens:

### Stage 1: Discovery, Design Systems & Taste Persistence
* **[`create-design-md`](https://github.com)** *(ibelick)* — Scans existing repositories or live URLs to extract evidence-based tokens into `DESIGN.md`.
* **[`ui-ux-pro-max`](https://github.com)** *(NextLevelBuilder)* — Generates structured design systems, color palettes, font pairings, and UX guidelines.
* **[`learn-taste`](https://ui-skills.com)** *(Emil Kowalski)* — Converts your iterative UI feedback into permanent rules inside `DESIGN.md` so you never repeat preferences.

### Stage 2: UI Generation & Stack Precision
* **[`frontend-design`](https://github.com)** *(Anthropic)* — Enforces strong visual hierarchy, custom typography, and distinctive layouts free of generic AI templates.
* **[`shadcn`](https://shadcn.com)** *(shadcn/ui)* — Inspects your project's actual aliases, Tailwind configuration, and installed components before generating UI code.
* **[`mobile-native`](https://ui-skills.com)** *(Emil Kowalski)* — Applies native-feeling mobile web rules (touch targets, iOS safe areas, `100dvh` viewports, tap highlights).

### Stage 3: Refactoring, Polish & Motion
* **[`impeccable`](https://github.com)** *(Paul Bakaus)* — Hands-on design refactoring with 24 slash commands (`/audit`, `/polish`, `/typeset`, `/bolder`) and 60+ local anti-slop checks.
* **[`improve-animations`](https://github.com)** *(Emil Kowalski)* — Crafts and audits restrained, hardware-accelerated micro-interactions and transitions.

### Stage 4: Auditing, Accessibility & Live Browser QA
* **[`improve-ui`](https://github.com)** *(ibelick)* — Strictly read-only UI surface auditor that outputs non-destructive implementation plans before modifying code.
* **[`web-design-guidelines`](https://github.com)** *(Vercel Labs)* — Deterministic 100+ rule linter covering focus states, forms, layout shifts, and UX edge cases.
* **[`fixing-accessibility`](https://github.com)** *(ibelick)* — Audits and fixes WCAG compliance, ARIA labels, keyboard navigation, focus traps, and color contrast.
* **[`webapp-testing`](https://github.com)** *(Anthropic)* — Spins up Playwright to capture desktop/mobile screenshots and visually verify rendered UI changes.

---

## Quick Start (Import Once)

### Option 1: Install via `npx skills` CLI (Recommended)
Run this single command inside any project to install the entire 12-skill pack:

```bash
npx skills add <your-username>/agent-ui-ux-skills --all
```

*(Append `-g` to install globally across all projects on your machine.)*

### Option 2: Add as a Git Submodule
1. Add `agent-ui-ux-skills` to your project:
   ```bash
   git submodule add https://github.com<your-username>/agent-ui-ux-skills.git .agent-skills
   ```
2. Point your agent's root `AGENTS.md` or config file to `.agent-skills/AGENTS.md` so it automatically loads the skill registry and 4-stage router at session start.

---

## Repository Structure

```text
agent-ui-ux-skills/
├── AGENTS.md                  # Universal agent instructions & 4-stage routing matrix
├── README.md                  # Documentation & quick-start guide
├── DESIGN.md                  # Starter template for project tokens, colors & typography
├── PRODUCT.md                 # Starter template for product & audience context
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

---

## Maintaining & Extending the Bundle

1. **Sync/Update All Installed Skills:** Run the **One-Line Sync Script** in Section 4 of `AGENTS.md`, review the updated `SKILL.md` files for safety, and commit `.agents/skills/`.
2. **Add a New Skill:**
   * Run `npx skills add <owner>/<repo> --skill <skill-name>`.
   * Add the skill to the appropriate stage table in `AGENTS.md`.
   * Append its install command to Section 4 of `AGENTS.md` and commit.

---

## License

This repository's configuration and `AGENTS.md` routing instructions are licensed under the **MIT License**. All bundled skills inside `.agents/skills/` retain their respective upstream open-source licenses.
