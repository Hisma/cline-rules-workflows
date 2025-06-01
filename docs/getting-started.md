# Getting Started with Cline Rules & Workflows

Welcome to the Cline Rules & Workflows system! This guide will help you understand both components and get started with your own setup.

## ⚠️ Critical: Understanding Prompt Injection

**Before you start**: Rules inject their entire content into every prompt sent to the LLM. This creates significant noise and token usage if multiple rules are active.

### Key Principles

- **Toggle-first approach** - Load many rules, activate few
- **Recommended baseline** - Keep `collaboration-rules.md` enabled for most tasks
- **Maximum recommendation** - 1 global rule + 1 project rule active at any time
- **Task-specific activation** - Enable additional rules only for current work, then disable
- **Prefer workflows** - Use workflows over rules when possible for cleaner prompts

## What Are Rules and Workflows?

### Rules (Use Sparingly)

Rules provide **persistent context** to Cline about your preferences, standards, and project requirements. When enabled, they automatically inject into every conversation.

- **⚠️ Prompt injection** - Full content added to every prompt when enabled
- **Toggle control** - Enable/disable through Cline UI switches
- **Persistent guidance** - Apply to all interactions while active
- **Best practice** - Keep most disabled, enable only what you need

### Workflows (Preferred for Most Tasks)

Workflows provide **step-by-step processes** for complex tasks. They're invoked on-demand when you need to execute a specific procedure.

- **On-demand execution** - Triggered using `/workflow-name.md` commands
- **Clean prompts** - Only inject content when explicitly invoked
- **Process automation** - Guide you through multi-step tasks
- **Actionable instructions** - Provide specific commands and verification steps

## Quick Start Paths

Choose your path based on what you want to set up first:

### Path 1: Start with Workflows (Recommended)

1. [Set up workflows](workflows/how-to-setup-workflows.md) - Clean, on-demand process automation
2. [Enable collaboration-rules.md](rules/how-to-setup-rules.md) - The recommended baseline global rule
3. [Add minimal additional rules](rules/how-to-setup-rules.md) - Only essential context (1-2 rules max)
4. [Use toggle strategy](integration/rules-vs-workflows.md) - Enable additional rules only when needed

### Path 2: Minimal Rules Setup (For context-focused users)

1. [Set up 1-2 global rules](rules/how-to-setup-rules.md) - Essential standards only
2. [Keep most rules disabled](rules/local-vs-global-rules.md) - Toggle-first approach
3. [Add workflows for processes](workflows/how-to-setup-workflows.md) - Clean automation

### Path 3: Library Approach (For experienced users)

1. [Understand prompt injection](integration/rules-vs-workflows.md) - Critical knowledge
2. [Create rule library](rules/how-to-setup-rules.md) - Many rules, most disabled
3. [Create workflow library](workflows/how-to-setup-workflows.md) - Process automation
4. [Master toggle strategy](integration/combined-development-approach.md) - Selective activation

## Directory Structure Overview

Here's how rules and workflows are organized:

```text
# Global (applies to all projects)
~/Cline/Rules/
├── coding-standards.md           # Global rules
├── collaboration-rules.md        # Global rules
├── documentation-requirements.md # Global rules
└── mcp-server-requirements.md    # Global rules

~/Cline/Workflows/
├── code-review-process.md         # Global workflows
├── project-setup.md               # Global workflows
├── project-update.md              # Global workflows
├── update-rules-workflows.md      # Global workflows
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

## Recommended Baseline: collaboration-rules.md

**For most users, the single most valuable rule is `collaboration-rules.md`.**

This global rule establishes effective collaboration patterns between you and Cline:

- **Focuses on process** - How to work together, not technical specifics
- **Minimal prompt noise** - Designed to be always-on without overwhelming prompts
- **Universal applicability** - Useful across all project types and tasks
- **Collaboration foundation** - Establishes clear communication and workflow patterns

**Recommendation**: Enable `collaboration-rules.md` as your baseline rule, then add task-specific rules only when needed.

## First Steps

### 1. Choose Your Starting Point

**New to Cline Rules & Workflows?**

- Start with [Workflows Setup](workflows/how-to-setup-workflows.md) - Clean, on-demand processes
- Enable `collaboration-rules.md` as your baseline global rule
- Practice toggle strategy with simple tasks

**Already using Cline?**

- **Critical**: Review [Rules vs Workflows](integration/rules-vs-workflows.md) - Understand prompt injection
- Audit current rules - disable most, keep only essential ones active
- Convert persistent processes to workflows for cleaner prompts

**Working on a team?**

- Establish toggle-first culture - educate team on prompt injection
- Create shared workflow library for common processes
- Limit active rules to 1-2 team standards maximum

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

### Starting Out (Toggle-First Mindset)

1. **Begin with workflows** - Start with 2-3 workflows, avoid rules initially
2. **Create rule library** - Build many rules but keep them disabled
3. **Practice toggling** - Enable rules only for specific tasks, then disable
4. **Monitor prompt size** - Check context window usage regularly

### Growing Your System (Selective Activation)

1. **Build library, activate selectively** - Create many options, use few at once
2. **Prefer workflows over rules** - Convert persistent rules to on-demand workflows
3. **Document toggle strategies** - Track which combinations work for different tasks
4. **Educate team members** - Share toggle-first approach and prompt injection awareness

### Maintenance (Clean Prompts)

1. **Regular toggle audits** - Monthly review of what's actually enabled
2. **Disable unused rules** - Turn off rules that aren't actively needed
3. **Optimize for efficiency** - Prefer workflows for most tasks
4. **Track prompt impact** - Monitor token usage and conversation quality

## Getting Help

### Documentation

- **[Rules Documentation](rules/)** - Everything about rules
- **[Workflows Documentation](workflows/)** - Everything about workflows
- **[Integration Guide](integration/)** - How they work together

### Examples

- **[Global Templates](../templates/global/)** - Universal rules and workflows
- **[Workspace Templates](../templates/)** - Project-specific examples
- **[This Project's Rules](../.clinerules/)** - Working example of docsite-workspace template
