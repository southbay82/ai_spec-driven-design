---
trigger: always_on
---

# Enforce Spec Adherence

## Purpose
This steering file ensures all decisions, code generation, and interactions in Windsurf's Cascade adhere strictly to project specifications in /spec/{feature_name}/. Reference specs in every response. Apply these rules in all workflows via callbacks like "Follow #enforce-spec.md for [phase]".

## General Rules
- **Adherence and Validation**: Always reference /spec/{feature_name}/requirements.md, design.md, tasks.md. Quote sections. Validate code/decisions against them; explain non-compliance and propose fixes.
- **Phased Approvals and Iterations**: Use phased approach (requirements, design, tasks). After each phase/update, prompt for explicit approval (e.g., "Do the [phase] look good? [yes/no/revisions]"). Iterate until "yes/approved/looks good". Do not proceed without approval. Offer to return to prior phases if gaps identified.
- **Insufficient Details**: If specs lack info, prompt user for clarification/targeted questions/suggestions. Do not assume.
- **Security/Privacy/Best Practices**: Prioritize secure, minimal code. Use placeholders for PII. Decline malicious requests. Focus on code-related tasks only.
- **Research Handling**: Conduct research in-thread (use web search if available or prompt user). Summarize findings, cite sources/links. Incorporate into design/tasks; no separate files.
- **Task Execution Rules**: Before any task, read all specs. Execute one task/sub-task at a time. Stop after completion for review. Recommend next if unspecified. Verify against requirements. Do not implement beyond requested task.
- **No Non-Coding Tasks**: In tasks.md/planning, include only code writing/modifying/testing. Avoid user testing, deployment, metrics, etc. (Automated tests OK for E2E).

## Phase-Specific Rules
### Requirements Phase
- Create /spec/{feature_name}/requirements.md if missing.
- Generate initial version from user idea without questions first.
- Format: # Feature: [Name] ## Introduction [summary] ## Requirements 1. User Story: As a [role], I want [feature], so that [benefit]. 1. [EARS: The system shall...] (hierarchical numbered list).
- Consider edge cases, UX, constraints, success criteria.
- After update, prompt: "Do the requirements look good? If so, move to design." Iterate until explicit approval.
- Suggest clarifications/expansions; ask targeted questions/options if needed.

### Design Phase
- Create /spec/{feature_name}/design.md if missing; ensure requirements exist.
- Identify research needs; conduct/summarize in-thread.
- Format sections: Overview, Architecture, Components and Interfaces, Data Models, Error Handling, Testing Strategy.
- Include diagrams (Mermaid if applicable), decisions/rationales.
- Address all requirements; ask user for input on tech decisions if needed.
- After update, prompt: "Does the design look good? If so, move to implementation plan." Iterate until approval.
- Return to requirements if gaps found.

### Tasks Phase
- Create /spec/{feature_name}/tasks.md if missing; ensure design exists.
- Follow: Convert design to LLM prompts for test-driven, incremental code gen. Prioritize best practices, no big jumps, build on prior, integrate all.
- Format: Numbered checkbox list (max 2 levels, e.g., - [ ] 1. [Objective: Write code...] - Sub-bullets: [info, refs to requirements sub-items]).
- Each task: Clear code objective, references to granular requirements, incremental.
- Cover all design/code aspects; prioritize TDD; sequence for early validation.
- Only code tasks; avoid listed non-coding (e.g., no deployment, but OK automated E2E tests).
- Offer return to prior phases if gaps.
- After update, prompt: "Do the tasks look good?" Iterate until approval.
- Communicate: Workflow for planning only; implement via separate /spec-task-execute.

This file steers all interactions toward iterative, spec-driven development.