# AI Spec-Driven Design

A comprehensive spec-driven development framework that enforces structured, iterative software development through AI-assisted workflows. Originally developed for Windsurf, but adaptable to other AI coding assistants like AWS Q CLI, Claude Code, and Cursor.

## Overview

This framework implements a phased approach to software development:
1. **Requirements Phase** - Define user stories and system requirements
2. **Design Phase** - Create architecture and technical specifications  
3. **Tasks Phase** - Break down implementation into manageable, testable tasks
4. **Execution Phase** - Implement tasks with continuous spec validation

## Project Structure

```
ai_spec-driven-design/
├── rules/
│   └── windsurf/
│       └── enforce-spect.md     # Core steering rules for spec adherence
└── commands/
    ├── spec-init.md             # Initialize new spec-driven project
    ├── spec-init-jira.md        # Initialize with Jira integration
    ├── spec-update.md           # Update existing specifications
    └── spec-execute-task.md     # Execute specific implementation tasks
```

## Installation

### For Windsurf

1. **Install Rules** (Steering Files):
   ```bash
   # Copy rules to your project's Windsurf configuration
   cp rules/windsurf/enforce-spect.md .windsurf/rules/
   ```

2. **Install Commands** (Workflows):
   ```bash
   # Copy all command workflows
   cp commands/*.md .windsurf/workflows/
   ```

3. **Verify Installation**:
   - Rules should appear in `.windsurf/rules/enforce-spect.md`
   - Commands should appear in `.windsurf/workflows/spec-*.md`

### For Other AI Coding Assistants

The framework can be adapted for other platforms by:

- **AWS Q CLI**: Convert commands to Q CLI workflow format
- **Claude Code**: Use as system prompts or project templates
- **Cursor**: Integrate as custom rules and workflow templates
- **Other Tools**: Adapt the markdown templates to your platform's format

## Usage

### Quick Start

1. **Initialize a New Project**:
   - Use the `spec-init` command to create initial specifications
   - Follow the phased approach: requirements → design → tasks

2. **Execute Tasks**:
   - Use `spec-execute-task` to implement specific features
   - Each task references and validates against specifications

3. **Update Specifications**:
   - Use `spec-update` when requirements or design changes
   - Maintains traceability throughout development

### Key Features

- **Spec Adherence**: All code generation validates against written specifications
- **Phased Approval**: Explicit approval required before proceeding to next phase
- **Incremental Development**: Tasks broken into manageable, testable chunks
- **Research Integration**: In-thread research with source citation
- **Security Focus**: Prioritizes secure coding practices and best practices

### Workflow Example

```
1. Run spec-init → Creates /spec/{feature}/requirements.md
2. Review/approve requirements → Proceed to design phase
3. Generate design.md → Architecture and technical decisions
4. Review/approve design → Proceed to tasks phase  
5. Generate tasks.md → Numbered implementation checklist
6. Execute tasks → Use spec-execute-task for each item
```

## Benefits

- **Consistency**: Standardized approach across all development phases
- **Traceability**: Clear links from requirements to implementation
- **Quality**: Built-in validation and review checkpoints
- **Documentation**: Specifications serve as living documentation
- **Adaptability**: Framework works with multiple AI coding platforms

## Contributing

This framework is designed to be extended and customized. Feel free to:
- Add new command templates for specific use cases
- Adapt rules for different development methodologies
- Create platform-specific integrations

## License

Adaptable for use with various AI coding assistance tools and platforms.
