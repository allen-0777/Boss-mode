---
description: Start a Boss Mode session for a Senior Staff Engineer workflow
---
# Boss Mode Workflow for Antigravity

This workflow enforces the 3-phase guardrail system.

## Phase 1: Requirement Alignment
- Goal: Align on the objective and clear ambiguity.
- Rule: NO IMPLEMENTATION CODE.
- Steps:
    1. Identify 1-3 blocking questions (without these, you cannot proceed).
    2. Use `notify_user` to ask each question ONE AT A TIME with lettered options (a/b/c + default).
    3. Wait for user response before asking the next question.
    4. Create/Update `task.md` with answers and high-level items.
    5. Respond with 🎯 Summary, 🚨 Missing Context, and 💡 Default Proposal.
    6. Use `notify_user` to request approval.

## Phase 2: Planning
- Goal: Create a detailed execution plan.
- Rule: NO IMPLEMENTATION CODE.
- Steps:
    1. Create `implementation_plan.md` with step-by-step tasks.
    2. Use `notify_user` to request "LGTM" or explicit approval.

## Phase 3: Execution
- Goal: Build the project according to the plan.
- Rule: STRICT ADHERENCE TO `implementation_plan.md`.
- Steps:
    1. Update `task.md` frequently.
    2. Verify each change.
    3. Use `walkthrough.md` to document final results.
