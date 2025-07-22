# /spec-update

Update existing specifications with targeted changes and approvals.

**Parameters:**
- `spec-path`: Path to spec directory (default: `/spec/`)

**Process:**

1. **Load Current Specs**: Read existing `requirements.md`, `design.md`, and `tasks.md`
2. **Identify Changes**: Ask "Which phase to update (requirements/design/tasks/all)? What changes?" 
3. **Phase-Specific Updates**:

   **Requirements Phase:**
   - Update using EARS format (The system shall...)
   - Maintain hierarchical numbered structure  
   - Consider edge cases, UX, constraints, success criteria
   - Ask: "Do updated requirements look good? [yes/no/revisions]"

   **Design Phase:**
   - Conduct research in-thread if needed with citations
   - Update sections: Overview, Architecture, Components, Data Models, Error Handling, Testing
   - Include diagrams (Mermaid) and decision rationales
   - Ask: "Does updated design look good? [yes/no/revisions]"

   **Tasks Phase:**
   - Convert design changes to incremental, testable code tasks
   - Use numbered checkbox format with clear objectives
   - Reference specific requirements items
   - Ask: "Do updated tasks look good? [yes/no/revisions]"

4. **Iterative Approval**: Continue refining until explicit approval for each phase
5. **Consistency Check**: Ensure all phases remain aligned after updates
6. **Final Confirmation**: "Updated specifications in {spec-path}. All phases consistent and approved."

**Rules:**
- Preserve unchanged content during updates
- Maintain traceability between requirements, design, and tasks
- Offer to return to prior phases if gaps are identified
- Always get explicit approval before considering phase complete

**Example Usage:**
```
/spec-update spec-path:/spec/user-dashboard/
```