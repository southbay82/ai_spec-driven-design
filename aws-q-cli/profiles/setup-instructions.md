# AWS Q CLI Profile Setup for Spec-Driven Development

## Quick Setup

### Option 1: Global Context (All Projects)
```bash
# Add spec-driven rules globally
q chat
> /context add --global path/to/aws-q-cli/rules/spec-driven-development.md
```

### Option 2: Project Profile (Recommended)
```bash
# Create a spec-driven development profile
q chat
> /profile create spec-driven-dev

# Add the rules to this profile
> /context add path/to/aws-q-cli/rules/spec-driven-development.md

# Switch to the profile when starting new projects
> /profile set spec-driven-dev
```

## Project-Specific Setup
For each new project, also add the project rules:

```bash
# In your project directory
mkdir -p .amazonq/rules
cp path/to/aws-q-cli/rules/spec-driven-development.md .amazonq/rules/

# Q CLI will automatically use these rules
```

## Usage Workflow

### Initialize New Feature
```bash
q chat
> I want to initialize a spec-driven project for [feature name]. 
> Please create the requirements, design, and tasks phases with approvals.
```

### Execute Tasks
```bash
q chat
> Execute task 1.1 from /spec/[feature-name]/tasks.md
> Validate against requirements and stop for review.
```

### Update Specifications
```bash
q chat
> Update the design phase in /spec/[feature-name]/ 
> [describe changes needed]
```

## Verification
Check your setup:
```bash
q chat
> /context show
# Should display your spec-driven development rules
> /profile
# Should show available profiles including spec-driven-dev
```