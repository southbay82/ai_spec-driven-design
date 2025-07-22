# /spec-execute

Execute a specific task from the spec-driven development plan.

**Parameters:**
- `spec-path`: Path to spec directory (e.g., `/spec/feature-name/`)  
- `task-id`: Optional task number (e.g., `1.1`). If not provided, will recommend next task.

**Process:**

1. **Load Specifications**: Read `requirements.md`, `design.md`, and `tasks.md` from the spec directory
2. **Task Selection**: 
   - If no task-id provided, review tasks.md and ask: "Next suggested: [id]. Proceed? [yes/no/other id]"
   - If task-id provided, locate and focus on that specific task
3. **Implementation**:
   - Execute ONLY the specified task
   - Generate code/tests as needed
   - Validate implementation against requirements
   - Reference specific requirement sections in your work
4. **Completion**: 
   - Present implementation
   - Ask: "Review complete? Proceed to next? [yes/no]"
   - Do NOT auto-continue to next task

**Rules:**
- Always reference and quote relevant sections from specifications
- Focus on one task at a time
- Stop after each task for user review
- Validate all code against the original requirements
- If specifications are unclear, ask for clarification rather than assuming

**Example Usage:**
```
/spec-execute spec-path:/spec/user-auth/ task-id:1.2
```