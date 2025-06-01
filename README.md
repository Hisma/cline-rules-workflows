# Cline Rules and Workflows

This repository contains a collection of rules and workflows for use with Cline, an AI assistant that helps with software development tasks.

## Overview

Cline uses rules and workflows to guide its behavior and provide structured approaches to common tasks. This repository serves as a central location for managing and sharing these resources.

- **Rules**: Define constraints, standards, and expectations for Cline's behavior
- **Workflows**: Provide step-by-step guides for accomplishing specific tasks

## Repository Structure

```text
├── README.md                   # This file
├── cline-rules-workflows.code-workspace  # VS Code workspace file
├── docs/                       # Documentation directory
│   └── documentation-guide.md  # Comprehensive documentation guide
├── templates/                  # Templates for different workspace types
│   ├── docsite-workspace/      # Documentation site workspace templates
│   │   └── workflows/          # Workflows for documentation sites
│   │       ├── markdown-linting.md  # Markdown linting workflow
│   │       └── project-cleanup.md   # Project cleanup workflow
│   └── global/                 # Global templates (apply to all workspaces)
│       ├── Rules/              # Global rules
│       │   └── collaboration-rules.md  # Collaboration guidelines
│       └── Workflows/          # General workflows (numbered by category)
│           ├── 01-project-setup.md     # Project setup workflow
│           ├── 02-verify-tech-stack.md # Tech stack verification
│           ├── 10-coding-standards-workflow.md  # Coding standards
│           ├── 11-documentation-standards-workflow.md  # Doc standards
│           ├── 20-documentation-planning.md  # Documentation planning
│           ├── 21-research-and-document.md   # Research process
│           ├── 22-create-project-docs.md     # Project documentation
│           ├── 23-create-api-docs.md         # API documentation
│           ├── 24-create-user-guides.md      # User guides
│           ├── 25-documentation-review.md    # Documentation review
│           ├── 30-project-update.md          # Project updates
│           ├── 31-update-rules-workflows.md  # Rules/workflows updates
│           ├── 32-code-review-process.md     # Code review process
│           └── 40-setup-mcp-servers.md       # MCP server setup
```

## MCP Server Requirements

Effective use of Cline rules and workflows requires MCP (Model Context Protocol) servers.  These are the recommended MCPs to get started:

- **Context7** - Framework documentation and API references
- **Brave Search** - Web research and fact-checking
- **Puppeteer** - Content extraction and web automation

**Setup Guide**: [Configuring MCP Servers](https://docs.cline.bot/mcp/configuring-mcp-servers)

- **note**: You can run the infrastructure setup workflow `40-setup-mcp-servers.md` to quickly set up these MCPs.

**Quick verification**: Check your MCP configuration in Cline settings at `MCP Servers -> Installed` to ensure these servers are active.

## Rules

Rules define constraints, standards, and expectations for Cline's behavior. They help ensure consistency and quality in Cline's outputs.

### ⚠️ Important: Prompt Injection & Toggle Usage

Rules inject their entire content into every prompt sent to the LLM. This creates significant noise and token usage if you have multiple rules active simultaneously.

### Global Rules

Global rules apply to all workspaces and provide foundational guidance for Cline.

**Best Practice**: Through extensive testing, we've found that the optimal approach is to have **only one global rule enabled at all times** (the `collaboration-rules.md` rule), and handle everything else with workflows as needed. This provides the best balance between guidance and performance.

- This global rule establishes how you and Cline work together effectively. It's designed to be the one rule you keep enabled for most tasks, as it focuses on human-in-the-loop collaboration patterns rather than technical specifics.

## Workflows

Workflows provide step-by-step guides for accomplishing specific tasks. They help ensure consistent approaches to common activities. Workflows are organized into categories and numbered to indicate the order in which they should typically be executed.

**Workflow Placement Tip**: Consider placing workflows at the project level (in `.clinerules/workflows/`) instead of the global level for better scope management. This is especially useful when:
- Creating workflows specific to a particular project
- Managing a large number of workflows
- Organizing workflows by project context
- Reducing cognitive load by showing only relevant workflows

While the global rule (collaboration-rules.md) provides consistent collaboration patterns across all projects, workflows can be more targeted and organized at the project level.

### General Workflows

These general-purpose workflows are organized into categories based on their purpose and the phase of development in which they are typically used. They can be placed at either the global level (`~/Cline/Workflows/`) or the workspace level (`.clinerules/workflows/`) based on your preference and project needs.

#### Project Initialization (01-09)

These workflows are used when setting up a new project:

- **01-project-setup**: Steps for setting up a new project
- **02-verify-tech-stack**: Steps for verifying the tech stack

#### Development Standards (10-19)

These workflows establish standards for development:

- **10-coding-standards-workflow**: Standards for code quality and style
- **11-documentation-standards-workflow**: Standards for documentation

#### Documentation Process (20-29)

These workflows guide the creation of documentation through a modular approach:

- **20-documentation-planning**: Planning documentation for a project
- **21-research-and-document**: Process for researching and documenting topics
- **22-create-project-docs**: Creating core project documentation
- **23-create-api-docs**: Creating API documentation
- **24-create-user-guides**: Creating user guides and tutorials
- **25-documentation-review**: Reviewing documentation for quality and accuracy

These documentation workflows can be used sequentially for a complete documentation process, or independently based on specific needs. For example:

1. Start with **20-documentation-planning** to establish your documentation strategy
2. Use **21-research-and-document** to gather necessary information
3. Create core documentation with **22-create-project-docs**
4. If applicable, document APIs using **23-create-api-docs**
5. Create user-facing documentation with **24-create-user-guides**
6. Review all documentation using **25-documentation-review**

A comprehensive documentation guide is also available at `docs/documentation-guide.md` with detailed best practices, templates, and quality checklists.

#### Maintenance and Updates (30-39)

These workflows are used for ongoing maintenance:

- **30-project-update**: Steps for updating an existing project
- **31-update-rules-workflows**: Steps for updating rules and workflows
- **32-code-review-process**: Process for reviewing code

#### Infrastructure (40-49)

These workflows deal with infrastructure setup:

- **40-setup-mcp-servers**: Setting up MCP servers

### Project-Specific Workflows

Project-specific workflows are tailored to particular types of projects:

#### Documentation Site Workflows

- **Markdown Linting**: Process for linting markdown files
- **Project Cleanup**: Steps for cleaning up a documentation site
- **Validate Documentation**: Steps for validating documentation

## Quick Start

### Method 1: Using Cline UI (Recommended)

#### Create Rules and Workflows

1. Click the "Manage Cline Rules & Workflows" button (⚖️) below the chat window
2. Select "Global" scope for rules/workflows that apply to all projects
3. Create new files with .md extension (e.g., collaboration-rules.md, 01-project-setup.md)
4. Copy content from our templates in templates/global/Rules/ and templates/global/Workflows/

Remember that you can place general workflows at either the global or workspace level based on your preference and project needs.

#### Create Project-Specific Rules and Workflows

1. Click the "Manage Cline Rules & Workflows" button (⚖️)
2. Select "Workspace" scope for project-specific customizations
3. Create files based on your project type:
   - Documentation Projects: Use templates from templates/docsite-workspace/
   - Web Applications: Use templates from templates/web-app-workspace/

#### Customize Templates (Keep Most Disabled)

1. Edit the created files to match your specific project needs and preferences
2. **Important**: Keep most rules/workflows disabled by default
3. Only enable one rule (collaboration-rules.md) and use workflows as needed
4. Templates provide a starting point - adapt them to your workflow

#### Use Toggle-First Workflow

1. Before starting any task, consider which specific workflows you need
2. Keep the collaboration-rules.md rule enabled, toggle workflows as needed
3. This keeps your prompts clean and focused

### Method 2: Using Command Line (Alternative)

#### Set Up Rules and Workflows:

```bash
# Create directories
mkdir -p ~/Cline/Rules
mkdir -p ~/Cline/Workflows

# Copy templates
cp templates/global/Rules/* ~/Cline/Rules/
cp templates/global/Workflows/* ~/Cline/Workflows/
```

Remember that you can also place general workflows at the project level by copying them to `.clinerules/workflows/` instead.

#### Set Up Project-Specific Rules and Workflows:

For Documentation Projects:

```bash
mkdir -p .clinerules/workflows
cp templates/docsite-workspace/rules/* .clinerules/
cp templates/docsite-workspace/workflows/* .clinerules/workflows/
```
