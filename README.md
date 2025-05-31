# My Cline Rules Setup

This is my personal repository for managing Cline rules, along with documentation explaining how global vs local rules work. Feel free to use this as a reference for setting up your own Cline rules system.

## What This Repository Contains

**Educational Content**: Complete guides on how Cline's rule system works
**My Personal Setup**: The actual rules and templates I use in my development workflow
**Reference Material**: Examples you can adapt for your own projects

This isn't meant to be a "clone and install" repository, but rather a learning resource and reference for building your own Cline rules system.

## Repository Structure

```
cline-rules/
├── README.md                          # This file
├── docs/                             # Educational documentation
│   ├── local-vs-global-rules.md      # How Cline's rule system works
│   ├── how-to-setup-rules.md         # Step-by-step setup guide
│   └── my-workflow.md                # My personal approach
├── my-global-rules/                  # My actual global rules
│   ├── coding-standards.md           # My coding preferences
│   ├── collaboration-patterns.md     # Human-AI interaction methodology
│   ├── documentation-requirements.md # How I document code
│   ├── security-guidelines.md        # My security practices
│   └── workflow-patterns.md          # My development workflows
├── my-project-templates/             # My project-specific templates
│   ├── web-app/                      # For web applications
│   ├── mobile-app/                   # For mobile projects
│   └── data-science/                 # For ML/data projects
└── examples/                         # Real examples from my projects
    ├── current-project-rules/        # Actual .clinerules I use
    └── before-after-comparisons/     # How my rules evolved
```

## How to Use This Repository

### 1. Learn About Cline Rules
Start by reading the [Local vs Global Rules](docs/local-vs-global-rules.md) guide to understand how Cline's rule system works.

### 2. Set Up Your Own Rules
Follow the [Setup Guide](docs/how-to-setup-rules.md) to create your own global and project-specific rules.

### 3. Reference My Setup
Browse through `my-global-rules/` and `my-project-templates/` to see how I organize my rules. Feel free to adapt anything that fits your workflow.

### 4. Manual Setup Steps
- **Global Rules**: Create `~/Documents/Cline/` and add your own `.md` files
- **Project Rules**: Create `.clinerules/` in your project root and add your own `.md` files
- **Customize**: Adapt my examples to match your coding style and preferences

## Rule Types

### Global Rules (`~/Documents/Cline/`)
- Apply to ALL Cline projects automatically
- Stored as markdown files in `~/Documents/Cline/`
- Perfect for coding standards, documentation requirements, and general workflows

### Project-Specific Rules (`.clinerules/`)
- Apply only to the specific project
- Stored in `.clinerules/` directory in project root
- Perfect for project-specific requirements, tech stack rules, and current sprint guidelines

## What You'll Find Here

- 📚 **Educational Guides**: Complete documentation on how Cline rules work
- 🛠️ **My Personal Rules**: The actual global rules I use across all projects
- 📁 **Project Templates**: Starter templates for different types of projects
- 💡 **Real Examples**: Actual rules from my current projects
- 🔄 **Evolution**: How my rules have improved over time

## Documentation

- [Local vs Global Rules](docs/local-vs-global-rules.md) - How Cline's rule system works
- [How to Setup Rules](docs/how-to-setup-rules.md) - Step-by-step guide for your own setup
- [My Workflow](docs/my-workflow.md) - My personal approach and philosophy

## My Approach

I believe in:
- **Consistency**: Global rules ensure consistent coding standards across all projects
- **Flexibility**: Project-specific rules allow for context-appropriate guidelines
- **Evolution**: Rules should improve based on experience and changing needs
- **Sharing**: Open documentation helps the community learn and improve

## License

MIT License - feel free to use and modify for your projects.

## Support

For questions about Cline itself, visit the [official Cline repository](https://github.com/cline/cline).

For issues with this rules repository, please open an issue on GitHub.
