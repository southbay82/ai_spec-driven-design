---
description: Executes a spec task, following execution rules.
---

# Name: spec-task-execute

## Parameters
- Name: spec-path  
  Type: string  
  Required: true  
  Description: e.g., /spec/feature-name/
- Name: task-id  
  Type: string  
  Required: false  
  Description: Task number (e.g., 1.1); if none, recommend next

## Prompt
Executing task in {spec-path}. ALWAYS reference #enforce-spec.md rules, including read all specs first.

1. Read requirements.md, design.md, tasks.md.

2. If no {task-id}, review tasks.md; recommend next: "Next suggested: [id]. Proceed? [yes/no/other id]".

3. For task: If sub-tasks, start with them. Focus ONLY on this task. Generate code/test as needed, verify vs requirements.

4. Respond with implementation. Stop; prompt: "Review complete? Proceed to next? [yes/no]". Do not auto-continue.

5. If questions (no execution), answer without implementing (e.g., "Next task is [id]").