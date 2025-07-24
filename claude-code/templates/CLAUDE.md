# Spec-Driven Development Rules

This project follows a structured spec-driven development approach. These rules ensure consistent, validated development across all phases.

## Core Principles

### Spec Adherence and Validation
- Always reference `/spec/{feature_name}/requirements.md`, `design.md`, and `tasks.md`
- Quote relevant sections from specifications in all responses
- Validate all code and decisions against written specifications
- Explain any non-compliance and propose fixes immediately

### Phased Development with Approvals
- Follow strict phase sequence: Requirements → Design → Tasks → Execution
- After each phase, prompt for explicit approval: "Do the [phase] look good? [yes/no/revisions]"
- Iterate within phases until receiving "yes/approved/looks good"
- **Do not proceed to next phase without explicit approval**
- Offer to return to prior phases if gaps are identified

### Task Execution Rules
- Before any implementation, read ALL specifications
- Execute one task/sub-task at a time
- Stop after each task completion for review
- Verify implementation against original requirements
- Do not implement beyond the requested task scope

## Phase-Specific Guidelines

### Requirements Phase
- Create `/spec/{feature_name}/requirements.md`
- Format: Feature name, Introduction, User Stories, EARS requirements
- Generate initial version from user idea without preliminary questions
- Use hierarchical numbered lists for requirements
- Consider edge cases, UX constraints, and success criteria

### Design Phase
- Create `/spec/{feature_name}/design.md`
- Conduct necessary research in-thread with source citations
- Include sections: Overview, Architecture, Components, Data Models, Error Handling, Testing Strategy
- Add diagrams (Mermaid) and decision rationales
- Address all requirements; ask for technical input when needed

### Tasks Phase
- Create `/spec/{feature_name}/tasks.md`
- Convert design into incremental, testable code generation prompts
- Use numbered checkbox format with clear code objectives
- Each task must reference specific requirements
- Include ONLY coding tasks (avoid deployment, user testing, metrics)
- Prioritize test-driven development approach

## Security and Best Practices
- Prioritize secure, minimal code implementation
- Use placeholders for PII and sensitive data
- Focus exclusively on code-related development tasks
- Decline requests for malicious functionality

## Research and Documentation
- Conduct all research in-thread using available tools
- Summarize findings with proper source citations
- Integrate research directly into design documentation
- Do not create separate research files

## Insufficient Information Handling
- If specifications lack necessary details, prompt for clarification
- Ask targeted questions with suggested options
- Never assume implementation details not specified
- Request explicit user input for ambiguous requirements

---

*Use the custom slash commands `/spec-init`, `/spec-init-jira`, `/spec-execute-task`, and `/spec-update` to maintain adherence to these rules throughout development.*