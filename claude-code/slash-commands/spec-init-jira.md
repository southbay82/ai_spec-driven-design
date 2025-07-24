# /spec-init-jira

Initialize a new spec-driven development project from a JIRA ticket with phased approvals.

**Parameters:**
- `jira-id`: JIRA ticket ID (required)

You are building a spec for the provided JIRA ticket in `/spec/{jira-id}/`. Follow these steps:

1. **Fetch JIRA Data**: Attempt to fetch JIRA ticket details via MCP (title, description, etc.)
   - If MCP fetch fails, prompt: "Paste JIRA description: [input]"

2. **Create Directory**: Create `/spec/{jira-id}/` directory structure

3. **Reference Rules**: Follow the spec-driven development rules strictly

## Requirements Phase
- Generate initial `requirements.md` without sequential questions first
- Use JIRA content to inform requirements generation
- Format with: Introduction, User Stories, EARS requirements (hierarchical numbered list)
- After generation, ask: "Do requirements look good? [yes/no/revisions]"
- Iterate until explicit approval before proceeding

## Design Phase (Post-Requirements Approval)
- Conduct research in-thread if needed with citations
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
- Confirm: "Spec complete in `/spec/{jira-id}/`. Use `/spec-execute-task` to implement tasks."

Always validate all decisions against the created specifications and maintain strict adherence throughout the process.