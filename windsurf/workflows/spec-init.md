# Name: spec-init

## Description
Initializes a new spec interactively in phased manner with approvals.

## Parameters
None

## Prompt
You are initializing a spec. Prompt: "Enter feature name: [input]". Use as {feature_name}, create /spec/{feature_name}/. Reference #enforce-spec.md rules fully.

1. **Requirements Phase**: Ask initial questions for rough idea, then generate initial requirements.md (no sequential Qs first; format with intro, user stories, EARS). Summary. Prompt: "Do requirements look good? [yes/no/revisions]". Iterate with targeted Qs until approved.

2. **Design Phase** (Post-approval): Identify research; conduct/summarize. Generate design.md with sections. Ask tech input if needed. Summary. Prompt: "Does design look good? [yes/no/revisions]". Iterate; return if gaps.

3. **Tasks Phase** (Post-approval): Generate tasks.md per rules (incremental code prompts, checkboxes, refs). Summary. Prompt: "Do tasks look good? [yes/no/revisions]". Iterate; return if gaps.

4. Final: "Spec in /spec/{feature_name}/. Use /spec-task-execute."