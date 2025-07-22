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
│   ├── generic/                 # Platform-agnostic rules
│   │   └── enforce-spect.md     # Core steering rules for any AI assistant
│   └── windsurf/                # Windsurf-specific rules
│       └── enforce-spect.md     # Windsurf-specific steering rules
├── commands/                    # Windsurf workflow commands
│   ├── spec-init.md             # Initialize new spec-driven project
│   ├── spec-init-jira.md        # Initialize with Jira integration
│   ├── spec-update.md           # Update existing specifications
│   └── spec-execute-task.md     # Execute specific implementation tasks
├── claude-code/                 # Claude Code integrations
│   ├── slash-commands/          # Custom slash commands
│   │   ├── spec-init.md         # /spec-init command
│   │   ├── spec-execute.md      # /spec-execute command
│   │   └── spec-update.md       # /spec-update command
│   └── templates/
│       └── CLAUDE.md            # Template project rules file
└── aws-q-cli/                   # AWS Q CLI integrations
    ├── rules/                   # Context rules for profiles/global
    │   └── spec-driven-development.md
    └── profiles/
        └── setup-instructions.md # Profile configuration guide
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

### For Claude Code

1. **Install Slash Commands**:
   ```bash
   # Copy slash commands to your Claude Code settings
   # (Adjust path based on your Claude Code configuration)
   cp claude-code/slash-commands/*.md ~/.claude/slash-commands/
   ```

2. **Install Project Rules**:
   ```bash
   # Copy template to your project root and customize as needed
   cp claude-code/templates/CLAUDE.md ./CLAUDE.md
   ```

3. **Verify Installation**:
   - Slash commands should be available: `/spec-init`, `/spec-execute`, `/spec-update`
   - Project rules should be active via `CLAUDE.md` in your project root

### For Other AI Coding Assistants

1. **Install Generic Rules**:
   ```bash
   # Create rules directory if it doesn't exist
   mkdir -p .ai-assistant/rules/
   
   # Copy generic rules
   cp rules/generic/enforce-spect.md .ai-assistant/rules/
   ```

### For AWS Q CLI

1. **Setup Global Context** (applies to all projects):
   ```bash
   q chat
   > /context add --global aws-q-cli/rules/spec-driven-development.md
   ```

2. **Setup Project Profile** (recommended):
   ```bash
   q chat
   > /profile create spec-driven-dev
   > /context add aws-q-cli/rules/spec-driven-development.md
   > /profile set spec-driven-dev
   ```

3. **Project-Specific Rules** (optional):
   ```bash
   # In your project directory
   mkdir -p .amazonq/rules
   cp aws-q-cli/rules/spec-driven-development.md .amazonq/rules/
   ```

4. **Verify Setup**:
   ```bash
   q chat
   > /context show  # Should display spec-driven rules
   > /profile       # Should show your profiles
   ```

### For Other AI Coding Assistants

1. **Adaptation Guide**:
   - **Cursor**: Create Cursor Rules for workflow guidance (custom slash commands not yet supported)
   - **Other Tools**: Adapt the markdown templates to your platform's format

3. **Customization**:
   - Edit the generic rules to match your platform's capabilities
   - Add platform-specific guidance where needed
   - Test with your AI assistant's workflow system

## Usage

### Quick Start

#### Windsurf Users
1. **Initialize a New Project**: Use the `/spec-init` workflow to create initial specifications
2. **Execute Tasks**: Use `/spec-execute-task` to implement specific features  
3. **Update Specifications**: Use `/spec-update` when requirements or design changes

#### Claude Code Users
1. **Initialize a New Project**: Run `/spec-init` to create initial specifications
2. **Execute Tasks**: Run `/spec-execute spec-path:/spec/feature-name/ task-id:1.1` to implement features
3. **Update Specifications**: Run `/spec-update` when requirements or design changes

**Note**: The slash commands are helpful tools, but standard prompting will also follow these rules when `CLAUDE.md` is present in your project. You don't need to use the commands exclusively.

#### Cursor Users
1. **Setup Project Rules**: Copy `rules/generic/enforce-spect.md` content into Cursor Rules
2. **Initialize Projects**: Use Agent Mode with natural language prompts following the phased approach
3. **Execute Tasks**: Reference specifications in chat and use Agent Mode for autonomous implementation

#### AWS Q CLI Users
1. **Setup Profile**: Create and switch to `spec-driven-dev` profile with rules loaded
2. **Initialize Projects**: Use natural language: "Initialize spec-driven project for [feature]"
3. **Execute Tasks**: Reference specifications: "Execute task 1.1 from /spec/[feature]/tasks.md"
4. **Context Persistence**: Use `q chat --resume` to maintain conversation context

#### All Platforms
- Follow the phased approach: requirements → design → tasks → execution
- Each task references and validates against specifications  
- Maintains traceability throughout development

### Key Features

- **Spec Adherence**: All code generation validates against written specifications
- **Phased Approval**: Explicit approval required before proceeding to next phase
- **Incremental Development**: Tasks broken into manageable, testable chunks
- **Research Integration**: In-thread research with source citation
- **Security Focus**: Prioritizes secure coding practices and best practices

### Workflow Examples

#### Windsurf Workflow
```
1. Run spec-init → Creates /spec/{feature}/requirements.md
2. Review/approve requirements → Proceed to design phase
3. Generate design.md → Architecture and technical decisions
4. Review/approve design → Proceed to tasks phase  
5. Generate tasks.md → Numbered implementation checklist
6. Execute tasks → Use spec-execute-task for each item
```

#### Claude Code Workflow
```
1. Run /spec-init → Creates /spec/{feature}/requirements.md
2. Review/approve requirements → Proceed to design phase
3. Generate design.md → Architecture and technical decisions
4. Review/approve design → Proceed to tasks phase  
5. Generate tasks.md → Numbered implementation checklist
6. Execute tasks → Use /spec-execute or standard prompting for each item
```

#### Cursor Workflow
```
1. Setup Cursor Rules with spec-driven guidelines
2. Use Agent Mode: "Initialize spec for [feature]" → Creates /spec/{feature}/requirements.md
3. Review/approve requirements → Proceed to design phase
4. Generate design.md → Architecture and technical decisions
5. Review/approve design → Proceed to tasks phase  
6. Generate tasks.md → Numbered implementation checklist
7. Execute tasks → Use Agent Mode referencing specifications
```

#### AWS Q CLI Workflow
```
1. Setup profile: q chat > /profile set spec-driven-dev
2. Initialize project: "Initialize spec-driven project for [feature]" → Creates /spec/{feature}/requirements.md
3. Review/approve requirements → Proceed to design phase
4. Generate design.md → Architecture and technical decisions
5. Review/approve design → Proceed to tasks phase
6. Generate tasks.md → Numbered implementation checklist  
7. Execute tasks → "Execute task 1.1 from /spec/[feature]/tasks.md"
```

**Notes**: 
- Claude Code: With `CLAUDE.md` in your project, automatically follows spec-driven rules in all interactions
- Cursor: Agent Mode provides autonomous workflow execution with specification validation  
- AWS Q CLI: Profiles and context rules provide persistent spec-driven guidance across all conversations

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

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
