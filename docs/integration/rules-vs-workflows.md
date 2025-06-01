# Cline Rules vs Workflows: Complete Guide

Understanding the difference between Cline Rules and Workflows is essential for effective AI-assisted development. They serve different purposes and have different storage locations.

## Overview

Cline has two distinct systems for customization:

1. **Rules** - Persistent guidance and context for how Cline should behave
2. **Workflows** - Executable sequences of actions that can be invoked on-demand

## Cline Rules

### Purpose

Rules provide persistent, system-level guidance to Cline. They define:

- Coding standards and conventions
- Documentation requirements
- Project-specific context
- Architecture guidelines
- Current development priorities

### Storage Locations

#### Global Rules

- **Directory**: `~/Documents/Cline/.clinerules/`
- **Format**: Markdown files (`.md`)
- **Scope**: Apply to ALL Cline projects automatically
- **Use Case**: Universal coding standards, documentation requirements, security guidelines

#### Project-Specific Rules

- **Directory**: `.clinerules/` in your project root
- **Format**: Markdown files (`.md`)
- **Scope**: Apply only to the current project
- **Use Case**: Project-specific tech stack, current sprint requirements, architecture decisions

### How Rules Work

- Rules are **automatically loaded** when Cline starts
- Global rules load first, then project rules
- Project rules can extend or override global rules
- Rules provide **persistent context** for every conversation

### Example Rule Structure

```tree
~/Documents/Cline/.clinerules/
├── coding-standards.md
├── documentation-requirements.md
└── security-guidelines.md

your-project/.clinerules/
├── 01-project-overview.md
├── 02-tech-stack.md
└── 03-current-requirements.md
```
## Cline Workflows

### Purpose

Workflows define executable sequences of actions for repetitive tasks. They can:

- Automate complex multi-step processes
- Chain together multiple tools and commands
- Handle repetitive development tasks
- Integrate with external tools and APIs

### Storage Locations

#### Global Workflows

- **Directory**: `~/Documents/Cline/.clinerules/workflows/`
- **Format**: Markdown files (`.md`)
- **Scope**: Available across all projects
- **Use Case**: Universal processes like PR reviews, deployment scripts, project setup

#### Project-Specific Workflows

- **Directory**: `.clinerules/workflows/` in your project root
- **Format**: Markdown files (`.md`)
- **Scope**: Available only in the current project
- **Use Case**: Project-specific deployment, testing, or build processes

### How Workflows Work

- Workflows are **invoked on-demand** using slash commands
- Type `/workflow-name.md` in chat to trigger
- Workflows can use Cline's built-in tools
- Can execute command-line tools and external APIs
- Can chain multiple actions in sequence

### Example Workflow Structure

```tree
~/Documents/Cline/.clinerules/
├── coding-standards.md       # Global rule
├── documentation.md          # Global rule
└── workflows/                # Global workflows directory
    ├── pr-review.md          # Global workflow
    └── deploy-service.md     # Global workflow

your-project/.clinerules/
├── 01-project-overview.md    # Project rule
├── 02-tech-stack.md          # Project rule
└── workflows/                # Project workflows directory
    ├── build-and-test.md     # Project workflow
    └── deploy-staging.md     # Project workflow
```
## Key Differences

| Aspect | Rules | Workflows |
|--------|-------|-----------|
| **Purpose** | Persistent guidance | Executable actions |
| **Activation** | Automatic | Manual (slash commands) |
| **When Used** | Every conversation | On-demand |
| **Content** | Guidelines, context | Step-by-step instructions |
| **Global Location** | `~/Documents/Cline/.clinerules/` | `~/Documents/Cline/.clinerules/workflows/` |
| **Project Location** | `.clinerules/` | `.clinerules/workflows/` |
| **Invocation** | Automatic | `/workflow-name.md` |

## Directory Structure Summary

```tree
~/Documents/Cline/.clinerules/
├── coding-standards.md       # Global rule
├── documentation.md          # Global rule
├── security.md               # Global rule
└── workflows/                # Global workflows directory
    ├── code-review-process.md    # Global workflow
    ├── project-setup.md          # Global workflow
    ├── project-update.md         # Global workflow
    ├── update-rules-workflows.md # Global workflow
    └── verify-tech-stack.md      # Global workflow

your-project/
├── .clinerules/
│   ├── 01-project-overview.md    # Project rule
│   ├── 02-tech-stack.md          # Project rule
│   └── workflows/                # Project workflows directory
│       ├── project-workflow.md   # Project workflow
│       └── deploy.md             # Project workflow
├── src/
└── ...
```
## Best Practices

### For Rules

- **Global Rules**: Keep general, widely applicable
- **Project Rules**: Be specific to project context
- **Content**: Focus on "what" and "why", not "how"
- **Organization**: Use numbered prefixes for loading order

### For Workflows

- **Global Workflows**: Universal processes (PR reviews, deployments)
- **Project Workflows**: Project-specific automation
- **Content**: Detailed step-by-step instructions
- **Tools**: Leverage Cline's built-in tools and external commands

## Examples

### Rule Example (coding-standards.md)

## Coding Standards

## General Principles
- Write clean, readable code
- Use consistent naming conventions
- Comment complex logic

## TypeScript Guidelines
- Use strict mode
- Prefer interfaces over types
- Always specify return types

### Workflow Example (pr-review.md)

## PR Review Workflow

You have access to the `gh` terminal command. Please review the PR that I specify.

## Steps
1. Get PR information: `gh pr view <PR-number> --json title,body,comments`
2. Get the diff: `gh pr diff <PR-number>`
3. Analyze changes and provide feedback
4. Ask user for approval decision
5. Execute: `gh pr review <PR-number> --approve --body "message"`

## Troubleshooting

### Rules Not Loading

- Check file location: `~/Documents/Cline/.clinerules` for global rules
- Verify `.clinerules` directory exists at the project root for project rules
- Ensure files have `.md` extension

### Workflows Not Found

- Check file location: `~/Documents/Cline/.clinerules/workflows` for global workflows
- Verify workflow files are in project `.clinerules/workflows` at the project root for project workflows
- Use exact filename: `/workflow-name.md`

### Mixed Content

- **Rules** should contain guidance, not executable steps
- **Workflows** should contain executable instructions, not general guidance
- Keep them separate for clarity

## Summary

- **Rules** = Persistent guidance (automatic)
- **Workflows** = Executable actions (on-demand)
- **Global Rules** = `~/Documents/Cline/.clinerules`
- **Global Workflows** = `~/Documents/Cline/.clinerules/workflows`
- **Project Rules** = `.clinerules`
- **Project Workflows** = `.clinerules/workflows`
- **Invoke Workflows** = `/workflow-name.md`

Understanding this distinction will help you organize your Cline customizations effectively and avoid confusion between persistent guidance and executable automation.
