# 🎯 Project Goals
Boss Mode is an advanced prompt framework and workflow plugin designed specifically for AI development agents (e.g., Cursor, Cline, Superpowers). Its core mission is to transform AI from a "clueless junior coder" into a "Senior Staff Engineer" — forcing the AI to clarify requirements, propose architectural designs, and obtain your approval before writing a single line of code.

[繁體中文](file:///Users/liyuchan/Desktop/Boss-Mode/readme.md) | [English](file:///Users/liyuchan/Desktop/Boss-Mode/README_EN.md)

🚨 **Pain Points Solved**
When a user (The Boss) gives high-level or vague instructions (e.g., "Add a dashboard to view revenue"), traditional AI agents often "hallucinate" missing details and instantly produce massive amounts of buggy code. This leads to:
- Unnecessary technical debt.
- Broken architectures or database performance issues.
- Wasted API tokens and endless debugging loops.

💡 **Core Mechanism: 3-Phase Guardrails**
Boss Mode implements a strict State Machine:

**Phase 1: Requirement Alignment (No Implementation Code Allowed)**
AI must produce: **Goal Alignment (Summary)**, **Missing Context**, and a **Default Proposal**, then explicitly request your approval.

**Phase 2: Planning (No Implementation Code Allowed)**
Once the proposal is approved, AI generates a step-by-step execution plan in Markdown format (`PLAN.md`).

**Phase 3: Execution**
Only after you reply "LGTM" or approve the plan, the AI is "unlocked" to start writing code step-by-step.

🛠️ **Tech Stack & Supported Platforms**
This is a Prompt-as-Code project with zero dependencies, perfectly compatible with:
- **Cursor IDE**: Configured via `.cursorrules`.
- **Cline (Formerly Claude Dev) / Roo Code**: Configured via Custom Instructions.
- **Superpowers (obra/superpowers)**: Configured via `.skill.md` definitions.
- **Claude Code CLI**: Configured via `CLAUDE.md` or skills.
- **General LLMs**: ChatGPT, Claude, Gemini (as System Prompts).

🚀 **Quick Start**

**Cursor Users**: Copy [integrations/cursor/.cursorrules](file:///Users/liyuchan/Desktop/Boss-Mode/integrations/cursor/.cursorrules) to your project root.

**Superpowers Users**: Import [integrations/superpowers/boss-mode.skill.md](file:///Users/liyuchan/Desktop/Boss-Mode/integrations/superpowers/boss-mode.skill.md).

**Cline Users**: Use [integrations/cline/custom-instructions.md](file:///Users/liyuchan/Desktop/Boss-Mode/integrations/cline/custom-instructions.md) for your Custom Instructions.

**Claude Code Users**: Place [integrations/claude-code/CLAUDE.md](file:///Users/liyuchan/Desktop/Boss-Mode/integrations/claude-code/CLAUDE.md) in your project root, or [integrations/claude-code/boss-mode.skill.md](file:///Users/liyuchan/Desktop/Boss-Mode/integrations/claude-code/boss-mode.skill.md) in `.claude/skills/`.

**Trigger**: Simply type: "I want to develop [feature], start Boss Mode."
