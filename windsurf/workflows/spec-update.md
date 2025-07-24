---
description: Updates existing spec, targeting phases with approvals.
---

# Name: spec-update

## Parameters
- Name: spec-path  
  Type: string  
  Required: false  
  Description: e.g., /spec/feature-name/ (default /spec/)

## Prompt
Updating {spec-path}. Reference #enforce-spec.md rules.

1. Load files. Prompt: "Phase to update (requirements/design/tasks/all)? Changes? [input]". Gather iteratively.

2. For each phase: Update per format/rules (e.g., EARS for requirements). Summary/diff. Prompt: "Does updated [phase] look good? [yes/no/revisions]". Iterate until approved. Return to prior if gaps.

3. If research needed (design), conduct in-thread. Overwrite preserving unchanged.

4. Final: "Updated in {spec-path}. Adheres to rules."