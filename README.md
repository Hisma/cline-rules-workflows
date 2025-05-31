# Cline Rules and Workflows

A comprehensive guide and template collection for customizing Cline's behavior through rules and workflows. Learn how these systems work and get started with ready-to-use templates for different project types.

## What Are Rules and Workflows?

**Rules** provide persistent context to Cline about your preferences, standards, and project requirements. They're automatically loaded and inform every conversation.

**Workflows** provide step-by-step processes for complex tasks. They're invoked on-demand when you need to execute specific procedures.

Both systems support **global** (all projects) and **workspace** (project-specific) scoping.

## MCP Server Requirements

Effective use of Cline rules and workflows requires MCP (Model Context Protocol) servers. These are essential tools that every Cline user should configure:

- **Context7** - Framework documentation and API references
- **Brave Search** - Web research and fact-checking
- **Puppeteer** - Content extraction and web automation

**Setup Guide**: [Configuring MCP Servers](https://docs.cline.bot/mcp/configuring-mcp-servers)

Quick verification: Check your MCP configuration in Cline settings to ensure these servers are active.

## Template Overview

This repository provides templates for different project types:

### Global Templates (`templates/global/`)
Apply to all your projects:
- **Rules**: Coding standards, documentation requirements, MCP server setup
- **Workflows**: Research processes, tech stack verification, code review

### Workspace Templates
Project-specific implementations:
- **Documentation Sites** (`templates/docsite-workspace/`) - For technical documentation projects
- **Web Applications** (`templates/web-app-workspace/`) - For web development projects

## Quick Start

### 1. Set Up Global Rules and Workflows
```bash
# Create global directory
mkdir -p ~/Documents/Cline/.clinerules/workflows

# Copy global templates
cp templates/global/rules/* ~/Documents/Cline/.clinerules/
cp templates/global/workflows/* ~/Documents/Cline/.clinerules/workflows/
```

### 2. Set Up Project-Specific Rules and Workflows

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

### 3. Customize Templates
Edit the copied files to match your specific project needs and preferences.

## How It Works

### Rules (Automatic)
- **Global**: `~/Documents/Cline/.clinerules/` - Loaded for all projects
- **Workspace**: `.clinerules/` - Loaded for current project only
- **Loading**: Automatic when Cline starts, global rules first, then workspace rules

### Workflows (On-Demand)
- **Global**: `~/Documents/Cline/.clinerules/workflows/` - Available in all projects
- **Workspace**: `.clinerules/workflows/` - Available in current project only
- **Usage**: Invoke with `/workflow-name.md` in Cline chat

## Repository Structure

```
├── docs/                          # Detailed documentation
│   ├── getting-started.md         # Comprehensive setup guide
│   ├── rules/                     # Rules documentation
│   ├── workflows/                 # Workflows documentation
│   └── integration/               # How rules and workflows work together
├── templates/                     # Ready-to-use templates
│   ├── global/                    # Templates for all projects
│   │   ├── rules/                 # Global rules templates
│   │   └── workflows/             # Global workflows templates
│   ├── docsite-workspace/         # Documentation project templates
│   │   ├── rules/                 # Documentation-specific rules
│   │   └── workflows/             # Documentation workflows
│   └── web-app-workspace/         # Web application templates
│       ├── rules/                 # Web app-specific rules
│       └── workflows/             # Web development workflows
```

## Key Features

### Research-Driven Development
Templates include workflows that leverage MCP servers for:
- Comprehensive web research using Brave Search
- Content extraction from official sources with Puppeteer
- Framework documentation access through Context7
- Fact-checking and verification processes

### Structured Templates
- Consistent organization across project types
- Customizable for specific needs
- Version controlled and maintainable
- Community-focused for sharing and collaboration

### Progressive Complexity
- Start with basic global rules
- Add project-specific customizations
- Implement advanced research workflows
- Scale to team and organizational standards

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

## Best Practices

1. **Start Simple** - Begin with basic global rules, add complexity gradually
2. **Use MCP Servers** - Essential for research-driven development and accurate documentation
3. **Customize Templates** - Adapt provided templates to your specific needs
4. **Version Control** - Track your rules and workflows in Git
5. **Team Coordination** - Establish shared global rules for consistency

## Support

- **Documentation Issues** - Check the docs/ folder for detailed guidance
- **Template Questions** - Review template files and their comments
- **MCP Setup** - See [official Cline MCP documentation](https://docs.cline.bot/mcp/configuring-mcp-servers)
- **Community** - Share your successful patterns and improvements

## Contributing

This repository provides a foundation for Cline customization. Feel free to:
- Adapt templates for your needs
- Share successful patterns
- Contribute improvements
- Create new project type templates

---

**Note**: This project demonstrates the docsite-workspace template in action. The `.clinerules/` directory contains the actual rules and workflows used to maintain this documentation.
