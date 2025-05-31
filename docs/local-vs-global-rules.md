# Local vs Global Cline Rules

Understanding the difference between local (project-specific) and global Cline rules is crucial for effective AI-assisted development.

## Overview

Cline supports two types of rule configurations:

1. **Global Rules** - Apply to ALL your Cline projects
2. **Local Rules** - Apply only to a specific project

## Global Rules

### Location
- **Directory**: `~/Documents/Cline/.clinerules/`
- **Format**: Markdown files (`.md`)
- **Introduced**: Cline v3.17 (Global Workflows feature)

### Characteristics
- ✅ **Universal Application**: Automatically loaded for every Cline project
- ✅ **Cross-Project Consistency**: Ensures consistent coding standards across all work
- ✅ **Device Synchronization**: Can be synced across multiple machines
- ✅ **Team Standards**: Perfect for organization-wide coding guidelines

### Best Use Cases
- Coding standards and conventions
- Documentation requirements
- Security guidelines
- Preferred technology stacks
- General development workflows
- Code review criteria
- Testing approaches
- Git commit message formats

### Example Global Rules Structure
```
~/Documents/Cline/.clinerules/
├── coding-standards.md          # Language-agnostic coding rules
├── documentation-requirements.md # How to document code
├── security-guidelines.md       # Security best practices
├── git-workflow.md             # Git commit and branching standards
└── testing-standards.md        # Testing approaches and requirements
```

## Local Rules (Project-Specific)

### Location
- **Directory**: `.clinerules/` in your project root
- **Format**: Markdown files (`.md`)
- **Original Cline feature**: Available since early versions

### Characteristics
- ✅ **Project-Specific**: Only applies to the current project
- ✅ **Contextual**: Can reference specific files, frameworks, or project requirements
- ✅ **Flexible**: Can override or extend global rules for specific needs
- ✅ **Version Controlled**: Lives with your project code

### Best Use Cases
- Project-specific technology stack rules
- Current sprint or milestone requirements
- Project architecture guidelines
- Specific API or framework usage
- Database schema conventions
- Project-specific naming conventions
- Current feature development guidelines

### Example Local Rules Structure
```
your-project/
├── .clinerules/
│   ├── 01-project-overview.md    # What this project does
│   ├── 02-tech-stack.md          # Specific technologies used
│   ├── 03-architecture.md        # Project structure and patterns
│   ├── 04-current-sprint.md      # Current development focus
│   └── 05-api-guidelines.md      # Project-specific API rules
├── src/
└── ...
```

## Rule Hierarchy and Precedence

### How Rules Are Applied
1. **Global rules** are loaded first from `~/Documents/Cline/.clinerules/`
2. **Local rules** are loaded second from `.clinerules/`
3. **Local rules can extend or override global rules** for project-specific needs

### Example Hierarchy
```
Global Rule (coding-standards.md):
"Use TypeScript for all new code"

Local Rule (tech-stack.md):
"This legacy project uses JavaScript. Follow existing patterns but consider TypeScript for new major features."
```

## File Naming and Organization

### Global Rules Naming
- Use descriptive, category-based names
- Consider alphabetical ordering for consistency
- Examples:
  - `01-coding-standards.md`
  - `02-documentation.md`
  - `03-security.md`
  - `04-testing.md`

### Local Rules Naming
- Use numbered prefixes for loading order
- Include project context
- Examples:
  - `01-project-overview.md`
  - `02-tech-stack.md`
  - `03-current-sprint.md`
  - `04-specific-requirements.md`

## Migration Strategies

### From Custom Instructions to Global Rules
If you currently use Cline's "Custom Instructions" feature:

1. **Extract universal rules** → Move to global rules
2. **Keep project-specific rules** → Convert to local rules
3. **Test incrementally** → Verify rules work as expected

### From Local to Global Rules
When you find local rules that apply to multiple projects:

1. **Generalize the rule** → Remove project-specific references
2. **Move to global rules** → Add to `~/Documents/Cline/.clinerules/`
3. **Update local rules** → Remove redundant content
4. **Test across projects** → Ensure compatibility

## Best Practices

### Global Rules
- ✅ Keep them general and widely applicable
- ✅ Focus on standards that rarely change
- ✅ Use clear, descriptive language
- ✅ Avoid project-specific references
- ❌ Don't include temporary or experimental guidelines

### Local Rules
- ✅ Be specific to the project context
- ✅ Reference specific files, APIs, or frameworks
- ✅ Include current development priorities
- ✅ Update regularly as the project evolves
- ❌ Don't duplicate global rules unnecessarily

### Rule Writing
- ✅ Use clear, actionable language
- ✅ Provide examples when helpful
- ✅ Organize content logically
- ✅ Keep rules focused and concise
- ❌ Avoid overly complex or contradictory rules

## Troubleshooting

### Rules Not Loading
1. **Check file location**: Ensure files are in correct directories
2. **Verify file format**: Must be `.md` (Markdown) files
3. **Restart Cline**: Sometimes requires restart to pick up new rules
4. **Check file permissions**: Ensure Cline can read the files

### Conflicting Rules
1. **Review hierarchy**: Remember local rules override global rules
2. **Clarify intent**: Make rule precedence explicit in documentation
3. **Test combinations**: Verify rules work well together
4. **Simplify when needed**: Remove redundant or conflicting rules

## Examples

See the `examples/` directory in this repository for real-world examples of both global and local rule configurations.
