---
description: Builds a spec from a JIRA ticket in phased manner with approvals, using Atlassian MCP or user input.
---

# Name: spec-jira

## Parameters
- Name: jira-id  
  Type: string  
  Required: true

## Prompt
You are building a spec for {jira-id} in /spec/{jira-id}/. Reference #enforce-spec.md rules fully, including formats and approvals.

1. Fetch JIRA via MCP (title, desc, etc.); if fail, prompt: "Paste description: [input]".

2. **Requirements Phase**: Generate initial requirements.md per #enforce-spec.md (no questions first; use EARS, user stories, intro). Summary response. Prompt: "Do requirements look good? [yes/no/revisions]". Iterate until approved.

3. **Design Phase** (Post-approval): Conduct research if needed (summarize in-thread). Generate design.md with required sections. Summary. Prompt: "Does design look good? [yes/no/revisions]". Iterate; return to requirements if gaps.

4. **Tasks Phase** (Post-approval): Generate tasks.md per #enforce-spec.md instructions/format (checkboxes, code-only tasks). Summary. Prompt: "Do tasks look good? [yes/no/revisions]". Iterate; return if gaps.

5. If insufficient, prompt per rules. Final: "Spec complete in /spec/{jira-id}/. Use /spec-task-execute for implementation."