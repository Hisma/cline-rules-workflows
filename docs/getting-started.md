# Getting Started with Cline Rules & Workflows

Welcome to the Cline Rules & Workflows system! This guide will help you understand both components and get started with your own setup.

## What Are Rules and Workflows?

### Rules

Rules provide **persistent context** to Cline about your preferences, standards, and project requirements. They're automatically loaded and inform every conversation.

- **Always active** - Loaded automatically when Cline starts
- **Provide context** - Help Cline understand your coding style, standards, and preferences
- **Persistent guidance** - Apply to all interactions without needing to be invoked

### Workflows

Workflows provide **step-by-step processes** for complex tasks. They're invoked on-demand when you need to execute a specific procedure.

- **On-demand execution** - Triggered using `/workflow-name.md` commands
- **Process automation** - Guide you through multi-step tasks
- **Actionable instructions** - Provide specific commands and verification steps

## Quick Start Paths

Choose your path based on what you want to set up first:

### Path 1: Start with Rules (Recommended for beginners)

1. [Set up global rules](rules/how-to-setup-rules.md) - Universal standards across all projects
2. [Create project rules](rules/local-vs-global-rules.md) - Project-specific context
3. [Add workflows later](workflows/how-to-setup-workflows.md) - Process automation

### Path 2: Start with Workflows (For process-focused users)

1. [Set up workflows](workflows/how-to-setup-workflows.md) - Process automation
2. [Add rules for context](rules/how-to-setup-rules.md) - Standards and preferences
3. [Combine both](integration/rules-vs-workflows.md) - Integrated approach

### Path 3: Set up Both Together (For experienced users)

1. [Understand the differences](integration/rules-vs-workflows.md) - How they work together
2. [Set up global rules](rules/how-to-setup-rules.md) - Foundation standards
3. [Set up global workflows](workflows/how-to-setup-workflows.md) - Common processes
4. [Create project-specific versions](integration/combined-development-approach.md) - Tailored approach

## Directory Structure Overview

Here's how rules and workflows are organized:

```# Global (applies to all projects)
~/Cline/Rules/
├── coding-standards.md           # Global rules
├── collaboration-rules.md        # Global rules
├── documentation-requirements.md # Global rules
└── mcp-server-requirements.md    # Global rules

~/Cline/Workflows/
├── code-review-process.md         # Global workflows
├── project-setup.md               # Global workflows
├── project-update.md              # Global workflows
└── verify-tech-stack.md           # Global workflows

# Project-specific (applies to current project only)

# Documentation Projects
your-docsite/.clinerules/
├── 01-project-overview.md        # Project rules
├── 02-tech-stack.md              # Project rules
├── 03-architecture.md            # Project rules
├── 04-current-requirements.md    # Project rules
├── 05-markdown-standards.md      # Markdown linting and quality standards
└── workflows/                    # Project workflows
    ├── project-cleanup.md
    └── research-and-document.md

# Web Application Projects
your-webapp/.clinerules/
├── 01-project-overview.md        # Project rules
├── 02-tech-stack.md              # Project rules
├── 03-architecture.md            # Project rules
├── 04-current-requirements.md    # Project rules
└── workflows/                    # Project workflows
    ├── deploy-to-staging.md
    └── project-cleanup.md
```
## Understanding the Hierarchy

### Rules Hierarchy

1. **Global rules** - From `~/Cline/Rules/` apply to all projects
2. **Project rules** - From `.clinerules/` in project root apply to the specific project

### Workflow Hierarchy

- **Global workflows** - From `~/Cline/Workflows/` apply to all projects
- **Project workflows** - From `.clinerules/workflows` in project root apply to the specific project
- **Invoking a Workflow** - To invoke a workflow, type `/workflow-name` in the chat
- **Toggle Control** - Enable/disable individual workflows using toggle switches in the Cline UI

## Common Use Cases

### For Individual Developers

**Rules:**

- Personal coding standards
- Preferred documentation style
- Security practices
- Git workflow preferences

**Workflows:**

- Code cleanup before commits
- Deployment procedures
- Dependency updates
- Performance testing

### For Teams

**Rules:**

- Team coding standards
- Project requirements
- Architecture decisions
- Quality thresholds

**Workflows:**

- Code review process
- Release procedures
- Testing protocols
- Incident response

### For Different Project Types

**Web Applications:**

- Rules: Framework standards, API guidelines, UI patterns
- Workflows: Build and deploy, testing, performance audits

**Documentation:**

- Rules: Writing style, structure requirements, citation standards, markdown linting standards
- Workflows: Research and document, review process, publication, markdown validation

## MCP Server Setup (Essential)

Before creating rules and workflows, set up MCP (Model Context Protocol) servers. These are essential for effective Cline usage:

### Required MCP Servers

- **Brave Search** - Web research and fact-checking
- **Puppeteer** - Content extraction and web automation
- **Context7** - Framework documentation (optional for basic usage)

### Quick Setup

1. **Open Cline Settings** - Click the gear icon in Cline
2. **Configure MCP Servers** - Follow the [official guide](https://docs.cline.bot/mcp/configuring-mcp-servers)
3. **Verify Setup** - Check that servers appear in your MCP configuration

### Why MCP Servers Matter

- **Research-Driven Development** - Verify information against current sources
- **Accurate Documentation** - Cross-reference with official documentation
- **Current Best Practices** - Stay updated with latest framework changes
- **Fact Checking** - Validate technical claims and procedures

## First Steps

### 1. Choose Your Starting Point

**New to Cline Rules & Workflows?**

- Start with [Rules Setup](rules/how-to-setup-rules.md)
- Create 2-3 basic global rules
- Test with a simple project

**Already using Cline?**

- Review [Rules vs Workflows](integration/rules-vs-workflows.md)
- Identify your most common processes
- Convert them to workflows

**Working on a team?**

- Establish team-wide global rules first
- Create project-specific rules for current project
- Add workflows for common team processes

## Templates and Examples

This repository provides templates to get you started:

### Global Templates

- **[Global Rules](../templates/global/Rules/)** - Universal standards for all projects
- **[Global Workflows](../templates/global/Workflows/)** - Common processes for all projects

### Workspace Templates

- **[Documentation Sites](../templates/docsite-workspace/)** - For technical documentation projects
  - Includes markdown standards and linting configuration
  - Quality assurance and validation processes
- **[Web Applications](../templates/web-app-workspace/)** - For web development projects
  - Development workflow optimization
  - Deployment and staging processes

### MCP Integration

- **[MCP Server Requirements](../templates/global/Rules/mcp-server-requirements.md)** - Essential MCP server setup
- **[Research Workflows](../templates/docsite-workspace/workflows/research-and-document.md)** - MCP-powered research processes

## Best Practices

### Starting Out

1. **Begin simple** - Start with 1-2 rules or workflows
2. **Focus on pain points** - Address your biggest frustrations first
3. **Test frequently** - Use your rules and workflows regularly
4. **Iterate based on use** - Refine based on real experience

### Growing Your System

1. **Add gradually** - Don't try to create everything at once
2. **Stay organized** - Use clear naming and organization
3. **Document changes** - Track what works and what doesn't
4. **Share learnings** - Help others benefit from your experience

### Maintenance

1. **Review regularly** - Monthly check of relevance and accuracy
2. **Update as needed** - Keep current with tool and process changes
3. **Remove unused items** - Clean up rules and workflows you don't use
4. **Version control** - Track changes to see evolution

## Getting Help

### Documentation

- **[Rules Documentation](rules/)** - Everything about rules
- **[Workflows Documentation](workflows/)** - Everything about workflows
- **[Integration Guide](integration/)** - How they work together

### Examples

- **[Global Templates](../templates/global/)** - Universal rules and workflows
- **[Workspace Templates](../templates/)** - Project-specific examples
- **[This Project's Rules](../.clinerules/)** - Working example of docsite-workspace template
