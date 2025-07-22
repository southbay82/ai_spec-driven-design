# Spec-Driven Development Rules

## Purpose
Enforce structured, iterative software development through AI-assisted workflows with explicit phased approvals.

## Development Phases
All development must follow this sequence:
1. **Requirements Phase** - Define user stories and system requirements
2. **Design Phase** - Create architecture and technical specifications  
3. **Tasks Phase** - Break down implementation into manageable, testable tasks
4. **Execution Phase** - Implement tasks with continuous spec validation

## Spec Adherence Rules
- Always reference `/spec/{feature_name}/requirements.md`, `design.md`, and `tasks.md`
- Quote relevant sections from specifications in all responses
- Validate all code and decisions against written specifications
- Explain any non-compliance and propose fixes immediately

## Phased Development with Approvals
- Use strict phase sequence: Requirements → Design → Tasks → Execution
- After each phase, prompt for explicit approval: "Do the [phase] look good? [yes/no/revisions]"
- Iterate within phases until receiving "yes/approved/looks good"
- **Do not proceed to next phase without explicit approval**
- Offer to return to prior phases if gaps are identified

## Requirements Phase Rules
- Create `/spec/{feature_name}/requirements.md`
- Format: Feature name, Introduction, User Stories, EARS requirements (The system shall...)
- Generate initial version from user idea without preliminary questions
- Use hierarchical numbered lists for requirements
- Consider edge cases, UX constraints, and success criteria
- After update, prompt: "Do the requirements look good? If so, move to design."

## Design Phase Rules
- Create `/spec/{feature_name}/design.md`
- Conduct necessary research and summarize findings with source citations
- Include sections: Overview, Architecture, Components, Data Models, Error Handling, Testing Strategy
- Add diagrams and decision rationales where appropriate
- Address all requirements; ask for technical input when needed
- After update, prompt: "Does the design look good? If so, move to implementation plan."

## Tasks Phase Rules
- Create `/spec/{feature_name}/tasks.md`
- Convert design into incremental, testable code generation prompts
- Use numbered checkbox format with clear code objectives
- Each task must reference specific requirements
- Include ONLY coding tasks (avoid deployment, user testing, metrics)
- Prioritize test-driven development approach
- After update, prompt: "Do the tasks look good?"

## Task Execution Rules
- Before any implementation, read ALL specifications
- Execute one task/sub-task at a time
- Stop after each task completion for review
- Verify implementation against original requirements
- Do not implement beyond the requested task scope

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