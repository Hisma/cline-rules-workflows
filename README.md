# Cline Rules and Workflows

A comprehensive guide and template collection for customizing Cline's behavior through rules and workflows. Learn how these systems work and get started with ready-to-use templates for different project types.

## What Are Rules and Workflows?

**Rules** provide persistent context to Cline about your preferences, standards, and project requirements. When enabled, they automatically inform every conversation. You can toggle individual rules on/off through the Cline UI.

**Workflows** provide step-by-step processes for complex tasks. They're invoked on-demand when you need to execute specific procedures. Like rules, individual workflows can be enabled/disabled through toggle switches in the UI.

Both systems support **global** (all projects) and **workspace** (project-specific) scoping.

## MCP Server Requirements

Effective use of Cline rules and workflows requires MCP (Model Context Protocol) servers.

- **Context7** - Framework documentation and API references
- **Brave Search** - Web research and fact-checking
- **Puppeteer** - Content extraction and web automation

**Setup Guide**: [Configuring MCP Servers](https://docs.cline.bot/mcp/configuring-mcp-servers)

Quick verification: Check your MCP configuration in Cline settings to ensure these servers are active.

## Template Overview

This repository provides templates for different project types:

### Global Templates (`templates/global/`)

Apply to all your projects:

- **Rules**: Coding standards, documentation requirements, MCP server setup, Collaboration Rules
- **Workflows**: Research processes, tech stack verification, code review, project set-up, project clean-up, project updates, and rules/workflows maintenance

### Workspace Templates

Project-specific implementations:

- **Documentation Sites** (`templates/docsite-workspace/`) - For technical documentation projects
  - Includes markdown standards and linting configuration
  - Research-driven content creation workflows
  - Quality assurance and validation processes
- **Web Applications** (`templates/web-app-workspace/`) - For web development projects
  - Development workflow optimization
  - Deployment and staging processes
  - Performance and security standards

## Quick Start

### Method 1: Using Cline UI (Recommended)

1. **Create Global Rules and Workflows**
   - Click the "Manage Cline Rules & Workflows" button (⚖️) below the chat window
   - Select "Global" scope for rules/workflows that apply to all projects
   - Create new files with `.md` extension (e.g., `coding-standards.md`, `project-setup.md`)
   - Copy content from our templates in `templates/global/Rules/` and `templates/global/Workflows/`

2. **Create Project-Specific Rules and Workflows**
   - Click the "Manage Cline Rules & Workflows" button (⚖️)
   - Select "Workspace" scope for project-specific customizations
   - Create files based on your project type:
     - **Documentation Projects**: Use templates from `templates/docsite-workspace/`
     - **Web Applications**: Use templates from `templates/web-app-workspace/`

3. **Customize and Enable Templates**
   - Edit the created files to match your specific project needs and preferences
   - Use toggle switches in the UI to enable/disable rules and workflows as needed
   - Templates provide a starting point - adapt them to your workflow

### Method 2: Using Command Line (Alternative)

**Set Up Global Rules and Workflows:**

```bash
# Create global directories
mkdir -p ~/Cline/Rules
mkdir -p ~/Cline/Workflows

# Copy global templates
cp templates/global/Rules/* ~/Cline/Rules/
cp templates/global/Workflows/* ~/Cline/Workflows/
```

**Set Up Project-Specific Rules and Workflows:**

**For Documentation Projects:**

```bash
mkdir -p .clinerules/workflows
cp templates/docsite-workspace/rules/* .clinerules/
cp templates/docsite-workspace/workflows/* .clinerules/workflows/
```

**For Web Applications:**

```bash
mkdir -p .clinerules/workflows
cp templates/web-app-workspace/rules/* .clinerules/
cp templates/web-app-workspace/workflows/* .clinerules/workflows/
```

## How It Works

### Rules (Automatic)

- **Global**: `~/Cline/Rules/` - Available for all projects
- **Workspace**: `.clinerules/` - Available for current project only
- **Loading**: When enabled, rules automatically inform conversations (global rules first, then workspace rules)
- **Toggle Control**: Enable/disable individual rules using toggle switches in the UI
- **UI Management**: Use the "Manage Cline Rules & Workflows" button (⚖️) to create, edit, and toggle rules

### Workflows (On-Demand)

- **Global**: `~/Cline/Workflows/` - Available in all projects
- **Workspace**: `.clinerules/workflows/` - Available in current project only
- **Usage**: Invoke with `/workflow-name.md` in Cline chat (only enabled workflows are available)
- **Toggle Control**: Enable/disable individual workflows using toggle switches in the UI
- **UI Management**: Use the "Manage Cline Rules & Workflows" button (⚖️) to create, edit, and toggle workflows

## Repository Structure

```text
├── docs/                          # Detailed documentation
│   ├── getting-started.md         # Comprehensive setup guide
│   ├── rules/                     # Rules documentation
│   ├── workflows/                 # Workflows documentation
│   └── integration/               # How rules and workflows work together
├── templates/                     # Ready-to-use templates
│   ├── global/                    # Templates for all projects
│   │   ├── Rules/                 # Global rules templates
│   │   └── Workflows/             # Global workflows templates
│   ├── docsite-workspace/         # Documentation project templates
│   │   ├── rules/                 # Documentation-specific rules
│   │   └── workflows/             # Documentation workflows
│   └── web-app-workspace/         # Web application templates
│       ├── rules/                 # Web app-specific rules
│       └── workflows/             # Web development workflows
```

## Documentation

### Getting Started

- **[Getting Started Guide](docs/getting-started.md)** - Comprehensive setup and usage
- **[Rules vs Workflows](docs/integration/rules-vs-workflows.md)** - Understanding the differences

### Rules Documentation

- **[How to Setup Rules](docs/rules/how-to-setup-rules.md)** - Step-by-step rules setup
- **[Local vs Global Rules](docs/rules/local-vs-global-rules.md)** - Scoping and hierarchy

### Workflows Documentation

- **[How to Setup Workflows](docs/workflows/how-to-setup-workflows.md)** - Workflow implementation
- **[Workflow Best Practices](docs/workflows/workflow-best-practices.md)** - Effective workflow design
- **[Creating Custom Workflows](docs/workflows/creating-custom-workflows.md)** - Building your own

### Integration

- **[Combined Development Approach](docs/integration/combined-development-approach.md)** - Using rules and workflows together

## Examples

This repository serves as a working example - it uses the docsite-workspace template for its own rules and workflows. Check `.clinerules/` to see the templates in action.

## Support

- **Documentation Issues** - Check the docs/ folder for detailed guidance
- **MCP Setup** - See [official Cline MCP documentation](https://docs.cline.bot/mcp/configuring-mcp-servers)
