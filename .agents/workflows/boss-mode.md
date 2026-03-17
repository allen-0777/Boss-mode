---
description: Start a Boss Mode session for a Senior Staff Engineer workflow
---
# Boss Mode Workflow for Antigravity
> **✨「讓 Boss Mode 的精神大腦，驅動 Antigravity 的強處理肉體。」**

This workflow enforces the 3-phase guardrail system using Antigravity's native artifact capabilities.

## Phase 1: Requirement Alignment
- Goal: Align on the objective and clear ambiguity.
- Rule: NO IMPLEMENTATION CODE.
- Steps:
    1. Identify 1-3 critical blocking questions.
    2. Use `notify_user` to ask each question **ONE AT A TIME**. Wait for user response before asking the next.
    3. Each question must include a clearly labeled **(Default)** option.
    4. Create/Update `task.md` with answers and high-level goal mapping.
    5. Respond with 🎯 Summary, 🚨 Missing Context, and 💡 Default Proposal.
    6. Use `notify_user` to request approval to move to Phase 2.

## Phase 2: Planning & Documentation
- Goal: Create a detailed blueprint and execution plan.
- Rule: NO IMPLEMENTATION CODE.
- Steps:
    1. **Create `implementation_plan.md`** with atomic, verifiable tasks.
    2. **Create `TECH_DOC.md`**: Document the proposed architecture, data models, and API endpoints before coding begins.
    3. Use `notify_user` to request "LGTM" or explicit approval.

## Phase 3: Execution & Continuous Documentation
- Goal: Implement the approved plan using agentic capabilities.
- Rule: STRICT ADHERENCE TO `implementation_plan.md`.
- Steps:
    1. Execute tasks one-by-one, updating `task.md` and `implementation_plan.md` frequently.
    2. **Update `TECH_DOC.md`** dynamically as implementation details evolve.
    3. **Finalize**: Upon completion, do a final review of `TECH_DOC.md` to ensure it matches the final codebase.
    4. Use `walkthrough.md` to document final results and validation.

