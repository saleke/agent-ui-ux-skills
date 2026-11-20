# `agent-ui-ux-skills`

A universal, plug-and-play bundle of UI/UX design engineering skills and routing instructions (`AGENTS.md`) for AI coding agents. Import this repository once to give your agent structured design intelligence, anti-slop guardrails, non-destructive UI auditing, active layout refactoring, and restrained motion patterns.

Works out of the box with **OpenCode**, **Claude Code**, **OpenAI Codex CLI**, **Cursor**, **Windsurf**, **GitHub Copilot**, and any [`agentskills.io`](https://agentskills.io)-compatible coding agent.

---

## Included Skills

| Skill | Author | Purpose |
| :--- | :--- | :--- |
| **[`frontend-design`](https://github.com)** | Anthropic | Establishes strong visual hierarchy, custom typography, and distinctive layouts while preventing generic AI templates. |
| **[`ui-ux-pro-max`](https://github.com)** | NextLevelBuilder | Generates structured design systems, color palettes, font pairings, and UX rules (`DESIGN.md`). |
| **[`impeccable`](https://github.com)** | Paul Bakaus | Hands-on design refactoring with 24 slash commands (`/audit`, `/polish`, `/typeset`, `/bolder`) and 60+ local anti-slop checks. |
| **[`improve-ui`](https://github.com)** | ibelick | Strictly read-only UI surface auditor that inspects existing screens against design evidence and outputs implementation plans. |
| **[`improve-animations`](https://github.com)** | Emil Kowalski | Audits and crafts purposeful, hardware-accelerated micro-interactions and transitions. |

---

## Quick Start (Import Once)

### Option 1: Install All Skills via CLI (Recommended)
Run this single command inside any project to pull all skills and instructions into your workspace:

```bash
npx skills add <your-username>/agent-ui-ux-skills --all
```

*(To install globally across all projects on your machine, append `-g`.)*

### Option 2: Point Your Agent to This Repo
1. Clone or add `agent-ui-ux-skills` as a Git submodule in your project:
   ```bash
   git submodule add https://github.com<your-username>/agent-ui-ux-skills.git .agent-skills
   ```
2. Reference `AGENTS.md` in your agent's instruction file or config so it automatically loads the skill routing rules at session start.

---

## Repository Structure

```text
agent-ui-ux-skills/
├── AGENTS.md                  # Universal agent instructions & task routing rules
├── README.md                  # Documentation & quick-start guide
├── DESIGN.md                  # Starter template for design tokens, colors & typography
├── PRODUCT.md                 # Starter template for product & audience context
└── .agents/
    └── skills/                # Pre-installed SKILL.md folders
        ├── frontend-design/
        ├── ui-ux-pro-max/
        ├── impeccable/
        ├── improve-ui/
        └── improve-animations/
```

---

## How the Agent Routes Tasks

Once `AGENTS.md` is loaded, your coding agent automatically selects the right skill based on what you ask it to do:

* **Building a new page or component from scratch:** Uses `ui-ux-pro-max` to define design tokens, followed by `frontend-design` for distinctive layout execution.
* **Reviewing existing UI safely (pre-PR):** Uses `improve-ui` to generate a read-only critique and implementation plan without touching your source code.
* **Refactoring & polishing interfaces:** Uses `impeccable` (`/audit`, `/polish`, `/normalize`, `/typeset`) to clean up spacing, hierarchy, and visual bugs directly.
* **Adding or fixing animations:** Uses `improve-animations` to keep transitions restrained, responsive, and GPU-accelerated.

---

## Extending This Bundle

To add new skills to `agent-ui-ux-skills`:

1. Install the new skill into `.agents/skills/`:
   ```bash
   npx skills add <owner>/<repo> --skill <skill-name>
   ```
2. Add a row to the **Core UI/UX Skill Registry** table in `AGENTS.md` specifying when the agent should invoke it.
3. Append its install command to the **One-Line Sync Script** in `AGENTS.md` and commit the updated `.agents/skills/` folder.

---

## License

This repository's configuration and `AGENTS.md` routing instructions are released under the **MIT License**. Individual skills inside `.agents/skills/` retain their respective upstream licenses.
