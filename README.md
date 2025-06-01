# Cline Rules and Workflows

This repository contains a collection of rules and workflows for use with Cline, an AI assistant that helps with software development tasks.

## Overview

Cline uses rules and workflows to guide its behavior and provide structured approaches to common tasks. This repository serves as a central location for managing and sharing these resources.

- **Rules**: Define constraints, standards, and expectations for Cline's behavior
- **Workflows**: Provide step-by-step guides for accomplishing specific tasks

## Repository Structure

```text
├── templates/                  # Templates for different workspace types
│   ├── docsite-workspace/      # Documentation site workspace templates
│   │   ├── rules/              # Rules for documentation sites
│   │   └── workflows/          # Workflows for documentation sites
│   ├── global/                 # Global templates (apply to all workspaces)
│   │   ├── Rules/              # Global rules
│   │   └── Workflows/          # Global workflows (numbered by category)
│   └── web-app-workspace/      # Web application workspace templates
│       ├── rules/              # Rules for web applications
│       └── workflows/          # Workflows for web applications
└── README.md                   # This file
```

## Rules

Rules define constraints, standards, and expectations for Cline's behavior. They help ensure consistency and quality in Cline's outputs.

### Global Rules

Global rules apply to all workspaces and provide foundational guidance for Cline:

- **Collaboration Rules**: Guidelines for effective collaboration

### Project-Specific Rules

Project-specific rules are tailored to particular types of projects:

- **Project Overview**: Description of the project and its goals
- **Tech Stack**: Technologies used in the project
- **Architecture**: System architecture and design
- **Current Requirements**: Current project requirements
- **Markdown Standards**: Standards for markdown files (for documentation sites)

## Workflows

Workflows provide step-by-step guides for accomplishing specific tasks. They help ensure consistent approaches to common activities. Workflows are organized into categories and numbered to indicate the order in which they should typically be executed.

### Global Workflows

Global workflows are organized into categories based on their purpose and the phase of development in which they are typically used:

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

## Usage

To use these rules and workflows with Cline:

1. Clone this repository to your local machine
2. Copy the relevant rules and workflows to your project's `.clinerules` directory
3. Customize the rules and workflows as needed for your project
4. Commit the changes to your project repository

For more detailed instructions, see the [Getting Started](docs/getting-started.md) guide.

## Contributing

Contributions to this repository are welcome! Please follow these steps:

1. Fork the repository
2. Create a new branch for your changes
3. Make your changes
4. Submit a pull request

Please ensure that your contributions follow the existing patterns and include appropriate documentation.

## License

This repository is licensed under the MIT License. See the LICENSE file for details.
