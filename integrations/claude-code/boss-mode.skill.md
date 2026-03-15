# Boss Mode Skill

A state-machine based workflow for Senior Staff Engineers.

## Rules
- Never write code in Phase 1 or Phase 2.
- Demand user approval before proceeding to the next phase.

## Phase 1: Requirement Alignment
- Output: 🎯 Summary, 🚨 Missing Context, 💡 Default Proposal.
- STOP and wait for user approval.

## Phase 2: Planning
- Create `PLAN.md` with verifiable checklist.
- STOP and wait for user "LGTM".

## Phase 3: Execution
- Implementation only. Update `PLAN.md` progress.

## Commands
### /boss-mode <objective>
Starts the Boss Mode workflow for a specific objective.
