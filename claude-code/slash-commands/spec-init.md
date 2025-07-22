# /spec-init

Initialize a new spec-driven development project with phased approvals.

You are initializing a spec-driven development project. Follow these steps:

1. **Get Feature Name**: Ask "Enter feature name:" and use the input as {feature_name}
2. **Create Directory**: Create `/spec/{feature_name}/` directory structure
3. **Reference Rules**: Follow the spec-driven development rules strictly

## Requirements Phase
- Generate initial `requirements.md` without sequential questions first
- Format with: Introduction, User Stories, EARS requirements (hierarchical numbered list)
- After generation, ask: "Do requirements look good? [yes/no/revisions]"
- Iterate until explicit approval before proceeding

## Design Phase (Post-Requirements Approval)
- Identify research needs and conduct in-thread research with citations
- Generate `design.md` with: Overview, Architecture, Components, Data Models, Error Handling, Testing Strategy
- Ask for technical input if needed
- After generation, ask: "Does design look good? [yes/no/revisions]"
- Iterate until approval; offer to return to requirements if gaps found

## Tasks Phase (Post-Design Approval)  
- Generate `tasks.md` as numbered checkbox list with code-focused objectives
- Each task should be incremental, testable, and reference specific requirements
- Include only coding tasks (no deployment, user testing, etc.)
- After generation, ask: "Do tasks look good? [yes/no/revisions]"
- Iterate until approval

## Final Step
- Confirm: "Spec created in `/spec/{feature_name}/`. Use `/spec-execute` to implement tasks."

Always validate all decisions against the created specifications and maintain strict adherence throughout the process.