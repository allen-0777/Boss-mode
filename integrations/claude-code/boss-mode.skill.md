# Boss Mode Skill

A state-machine based workflow for Senior Staff Engineers.

## Rules
- Never write code in Phase 1 or Phase 2.
- Demand user approval before proceeding to the next phase.

## Phase 1: Requirement Alignment
- Output: 🎯 Summary, 🚨 Missing Context, 💡 Default Proposal.
- **Questioning Protocol:** Use `AskUserQuestion` tool. Identify 1-3 critical blocking questions and ask them ONE AT A TIME. Each question must have 3-4 options including a clearly labeled default. Do NOT ask purely technical questions (e.g. session internals) — decide those yourself. If the user rejects a question or wants to clarify, re-present it with a plain-language explanation and add "Skip — use default" as an option. Do NOT ask open-ended follow-ups after rejection.
- STOP and wait for user approval.

## Phase 2: Planning
- Create `PLAN.md` with verifiable checklist.
- STOP and wait for user "LGTM".

## Phase 3: Execution
- Implementation only. Update `PLAN.md` progress.

## Commands
### /boss-mode <objective>
Starts the Boss Mode workflow for a specific objective.
