# How to Setup Your Own Cline Rules

This guide walks you through setting up your own Cline rules system, using this repository as a reference.

## Prerequisites

- Cline VSCode extension installed (v3.17+ for global rules support)
- MCP servers configured (essential for effective usage)
- Basic understanding of Markdown
- Familiarity with your development workflow

### MCP Server Setup (Required)
Before creating rules, ensure you have these MCP servers configured:
- **Brave Search** - For research and fact-checking
- **Puppeteer** - For content extraction
- **Context7** - For framework documentation (optional)

See the [official MCP setup guide](https://docs.cline.bot/mcp/configuring-mcp-servers) for configuration instructions.

## Step 1: Understand the System

Before setting up rules, read [Local vs Global Rules](local-vs-global-rules.md) to understand:
- How global rules work (`~/Documents/Cline/.clinerules/`)
- How project-specific rules work (`.clinerules/`)
- When to use each type

## Step 2: Set Up Global Rules

### Create the Global Rules Directory
```bash
mkdir -p ~/Documents/Cline/.clinerules
mkdir -p ~/Documents/Cline/.clinerules/workflows
```

### Start with Basic Global Rules
Create these foundational files:

**~/Documents/Cline/.clinerules/coding-standards.md**
```markdown
# Coding Standards

## General Principles
- Write clean, readable code
- Use consistent naming conventions
- Comment complex logic
- Follow language-specific best practices

## Code Style
- Use meaningful variable names
- Keep functions small and focused
- Avoid deep nesting
- Write self-documenting code
```

**~/Documents/Cline/.clinerules/documentation.md**
```markdown
# Documentation Requirements

## Code Documentation
- Document all public APIs
- Include usage examples
- Explain complex algorithms
- Keep comments up to date

## Project Documentation
- Maintain a clear README
- Document setup instructions
- Include troubleshooting guides
- Update changelog regularly
```

### Customize Based on Your Workflow
Look at the templates in `templates/global/rules/` and adapt them to your preferences:
- Coding standards you follow
- Documentation practices you prefer
- Security guidelines you implement
- MCP server requirements you need

## Step 3: Set Up Project-Specific Rules

### For New Projects
1. Create the rules and workflows directories:
   ```bash
   mkdir .clinerules
   mkdir .clinerules/workflows
   ```

2. Add project-specific files:
   ```bash
   touch .clinerules/01-project-overview.md
   touch .clinerules/02-tech-stack.md
   touch .clinerules/03-current-requirements.md
   ```

### Use Templates as Reference
Browse `templates/` for examples:
- **docsite-workspace/**: Rules for documentation projects
- **web-app-workspace/**: Rules for web applications
- **global/**: Universal rules for all projects

Copy and modify any templates that match your project type.

## Step 4: Test Your Setup

### Verify Global Rules
1. Open any project in VSCode with Cline
2. Start a new conversation
3. Ask: "What coding standards should I follow?"
4. Cline should reference your global rules

### Verify Project Rules
1. Open a project with `.clinerules/` directory
2. Start a new conversation
3. Ask: "What are the specific requirements for this project?"
4. Cline should reference both global and project rules

## Step 5: Iterate and Improve

### Track What Works
- Note which rules Cline follows consistently
- Identify rules that need clarification
- Observe which rules improve code quality

### Refine Over Time
- Update rules based on experience
- Add new rules for emerging patterns
- Remove rules that aren't helpful
- Keep rules concise and actionable

## Example Workflow

Here's how I typically set up rules for a new project:

1. **Start with globals**: My global rules provide the foundation
2. **Add project context**: Create `01-project-overview.md` explaining what the project does
3. **Specify tech stack**: Create `02-tech-stack.md` with specific technologies and frameworks
4. **Current focus**: Create `03-current-sprint.md` with immediate priorities
5. **Iterate**: Update project rules as the project evolves

## Common Patterns

### Global Rules Should Cover
- Language-agnostic coding standards
- Documentation requirements
- Security best practices
- Git workflow preferences
- Testing approaches

### Project Rules Should Cover
- Specific technology stack
- Project architecture
- Current development priorities
- Project-specific naming conventions
- API design guidelines

## Troubleshooting

### Rules Not Loading
- Check file locations and naming
- Ensure files have `.md` extension
- Restart VSCode if needed
- Verify Cline version (v3.17+ for global rules)

### Rules Too Verbose
- Keep rules concise and actionable
- Use bullet points instead of paragraphs
- Focus on the most important guidelines
- Split complex rules into separate files

### Conflicting Rules
- Make rule hierarchy clear in documentation
- Use project rules to override globals when needed
- Be explicit about exceptions and special cases

## Advanced Tips

### Rule Organization
- Use numbered prefixes for loading order
- Group related rules in the same file
- Keep file names descriptive
- Maintain consistent structure across projects

### Version Control
- Commit your global rules to a personal repository
- Include `.clinerules/` in your project repositories
- Track changes to see how rules evolve
- Share successful patterns with your team

### Team Collaboration
- Establish team-wide global rules
- Allow project-specific customizations
- Document rule decisions and rationale
- Review and update rules regularly

## Next Steps

1. **Start simple**: Begin with basic global rules
2. **Add gradually**: Introduce project rules as needed
3. **Monitor effectiveness**: Pay attention to how Cline uses your rules
4. **Share and learn**: Contribute back to the community

Remember: The goal is to make Cline more helpful for your specific workflow. Start with what matters most to you and build from there.
