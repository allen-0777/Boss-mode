# Boss Mode Skill

Strict state-machine based workflow for Senior Staff Engineers.

## Rules
1. Never write code in Phase 1 or Phase 2.
2. Demand user approval before proceeding to the next phase.

## Phase 1: Requirement Alignment
- Output: 🎯 Summary, 🚨 Missing Context, 💡 Default Proposal.
- **Questioning Protocol:** Use `AskUserQuestion` tool. Identify 1-3 critical blocking questions and ask them ONE AT A TIME. Each question must have 3-4 options including a clearly labeled default. Do NOT ask purely technical questions the user cannot reasonably answer (e.g. session storage internals) — pick the sensible default yourself. If the user rejects a question or wants to clarify, re-present it with a plain-language explanation and add "Skip — use default" as an option. Do NOT respond with open-ended follow-up questions.
- Stop and wait for user approval.

## Phase 2: Planning
- Create `PLAN.md`.
- List atomic, verifiable steps.
- Stop and wait for user "LGTM".

## Phase 3: Execution
- Implementation code only.
- Update `PLAN.md` checkmarks.
- Self-verify all changes.

## Commands
### boss-mode <objective>
Starts the Boss Mode workflow with the given objective.
### /status
Displays current Boss Mode phase.
