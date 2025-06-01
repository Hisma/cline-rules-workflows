# Markdown Standards and Linting

## Overview

This rule ensures all markdown content follows consistent formatting standards and passes automated linting. It establishes the `.markdownlint.json` configuration and provides guidelines for creating clean, professional documentation.

## Markdown Linting Configuration

**REQUIRED**: Create a `.markdownlint.json` file in the project root with this exact configuration:

```json
{
  "default": true,
  "MD001": true,
  "MD003": {
    "style": "atx"
  },
  "MD007": {
    "indent": 2
  },
  "MD013": false,
  "MD022": false,
  "MD024": {
    "siblings_only": true
  },
  "MD025": {
    "front_matter_title": "^\\s*title\\s*[:=]"
  },
  "MD031": false,
  "MD032": false,
  "MD033": {
    "allowed_elements": ["br", "details", "summary", "img", "kbd", "sub", "sup"]
  },
  "MD036": false,
  "MD040": true,
  "MD041": false,
  "MD046": {
    "style": "fenced"
  },
  "MD048": {
    "style": "backtick"
  }
}
```

### Configuration Explanation

- **MD001**: Enforce heading hierarchy (H1 → H2 → H3, no skipping levels)
- **MD003**: Use ATX-style headings (`#` format, not underlined)
- **MD007**: List indentation must be 2 spaces
- **MD013**: Line length disabled (no arbitrary length limits)
- **MD022**: Blank lines around headings disabled (too strict for documentation)
- **MD024**: Allow duplicate headings in different sections
- **MD025**: Allow multiple H1 headings with frontmatter titles
- **MD031**: Blank lines around fenced code blocks disabled (too strict)
- **MD032**: Blank lines around lists disabled (too strict)
- **MD033**: Allow specific HTML elements for enhanced formatting
- **MD036**: Emphasis as headings disabled (allows section labels)
- **MD040**: **ENFORCED** - All code blocks must specify language
- **MD041**: First line doesn't need to be H1 (allows frontmatter)
- **MD046**: Use fenced code blocks (```) not indented
- **MD048**: Use backticks for code blocks, not tildes

## Code Block Language Requirements

**CRITICAL**: Every fenced code block MUST specify a language. Use these guidelines:

### Directory Structures and File Trees

```text
project/
├── docs/
│   ├── getting-started.md
│   └── api/
├── src/
└── tests/
```

**Language**: `text` or `tree`

### Shell Commands and Terminal Output

```bash
npm install
git commit -m "Update documentation"
cd project-directory && npm start
```

**Language**: `bash`, `shell`, or `console`

### Configuration Files

**JSON Configuration:**
```json
{
  "name": "project",
  "version": "1.0.0"
}
```

**YAML Configuration:**
```yaml
name: project
version: 1.0.0
dependencies:
  - package-a
  - package-b
```

**XML Configuration:**
```xml
<configuration>
  <setting name="debug" value="true" />
</configuration>
```

### Programming Languages

**JavaScript:**
```javascript
function example() {
  return "Hello, world!";
}
```

**Python:**
```python
def example():
    return "Hello, world!"
```

**TypeScript:**
```typescript
interface Config {
  name: string;
  version: string;
}
```

### Markup and Styling

**HTML:**
```html
<div class="container">
  <h1>Title</h1>
</div>
```

**CSS:**
```css
.container {
  max-width: 1200px;
  margin: 0 auto;
}
```

**Markdown Examples:**
```markdown
# Heading 1
## Heading 2

- List item 1
- List item 2
```

### Generic Examples and Placeholders

```text
[Replace this with actual content]
Generic example without specific syntax
File paths: /path/to/file
```

**Language**: `text` or `plaintext`

## Heading Structure Standards

### Proper Heading Hierarchy

```markdown
# Document Title (H1)

## Major Section (H2)

### Subsection (H3)

#### Sub-subsection (H4)

##### Minor Section (H5)

###### Smallest Section (H6)
```

### Heading Best Practices

- **One H1 per document** (document title)
- **No skipping levels** (H1 → H2 → H3, not H1 → H3)
- **Descriptive headings** that clearly indicate content
- **Consistent capitalization** (Title Case or sentence case)

## List Formatting Standards

### Unordered Lists

```markdown
- First item
- Second item
  - Nested item
  - Another nested item
- Third item
```

### Ordered Lists

```markdown
1. First step
2. Second step
   1. Sub-step
   2. Another sub-step
3. Third step
```

### Task Lists

```markdown
- [ ] Incomplete task
- [x] Completed task
- [ ] Another incomplete task
```

## Link and Reference Standards

### Internal Links

```markdown
[Link Text](relative/path/to/file.md)
[Section Link](#heading-anchor)
[Documentation](../docs/getting-started.md)
```

### External Links

```markdown
[External Site](https://example.com)
[Documentation](https://docs.example.com/guide)
```

### Reference Links

```markdown
[Link Text][reference-id]

[reference-id]: https://example.com "Optional Title"
```

## Table Formatting

```markdown
| Column 1 | Column 2 | Column 3 |
|----------|----------|----------|
| Data 1   | Data 2   | Data 3   |
| Data 4   | Data 5   | Data 6   |
```

## Documentation-Specific Guidelines

### Template Placeholders

Use square brackets for placeholders that users should replace:

```markdown
**Project Name**: [Your Project Name]
**Version**: [Current Version]
**Author**: [Your Name]
```

### Section Organization

Standard documentation sections:

```markdown
# Document Title

## Overview
Brief description of the content

## Prerequisites
What users need before starting

## Step-by-Step Instructions
Detailed procedures

## Examples
Practical examples and use cases

## Troubleshooting
Common issues and solutions

## Notes
Additional information and references
```

### Code Examples with Context

Always provide context for code examples:

```markdown
**Create the configuration file:**

```json
{
  "name": "example",
  "version": "1.0.0"
}
```

**Run the installation command:**

```bash
npm install
```

## Validation and Testing

### Linting Commands

Install and run markdownlint:

```bash
npm install -g markdownlint-cli
markdownlint "**/*.md"
```

### Pre-commit Validation

Add to your workflow:

```bash
# Validate all markdown files
markdownlint "**/*.md"

# Fix auto-fixable issues
markdownlint "**/*.md" --fix
```

## Common Mistakes to Avoid

### ❌ Incorrect Code Blocks

```text
# Missing language specification
This will cause MD040 errors
```

### ✅ Correct Code Blocks

```text
# Proper language specification
This follows the standards
```

### ❌ Incorrect Heading Hierarchy

```markdown
# Title
### Skipped H2 - This is wrong
```

### ✅ Correct Heading Hierarchy

```markdown
# Title
## Proper H2
### Proper H3
```

### ❌ Inconsistent List Formatting

```markdown
* Mixed bullet styles
- Are not recommended
+ Use one style consistently
```

### ✅ Consistent List Formatting

```markdown
- Consistent bullet style
- Throughout the document
- Maintains readability
```

## Integration with Development Workflow

### Editor Configuration

**VS Code**: Install the "markdownlint" extension for real-time validation.

**Settings for VS Code** (`.vscode/settings.json`):

```json
{
  "markdownlint.config": {
    "extends": ".markdownlint.json"
  }
}
```

### Automated Validation

Include in CI/CD pipeline:

```yaml
# GitHub Actions example
- name: Lint Markdown
  run: |
    npm install -g markdownlint-cli
    markdownlint "**/*.md"
```

## Documentation Quality Standards

### Content Requirements

- **Clear headings** that describe the content
- **Complete code examples** with proper language specification
- **Consistent formatting** throughout all documents
- **Proper internal linking** between related documents
- **Accurate external links** that are regularly validated

### Maintenance Requirements

- **Regular linting** of all markdown files
- **Link validation** to ensure external links remain active
- **Content updates** to keep information current
- **Style consistency** across all documentation

## Implementation Checklist

When creating or editing markdown files:

- [ ] `.markdownlint.json` configuration file exists
- [ ] All code blocks specify appropriate language
- [ ] Heading hierarchy follows proper structure
- [ ] Lists use consistent formatting
- [ ] Links are properly formatted and functional
- [ ] Content follows documentation standards
- [ ] File passes `markdownlint` validation
- [ ] Content is clear and well-organized

## Notes

- This configuration is optimized for documentation projects
- The linting rules balance quality with practicality
- All team members should follow these standards
- Regular validation prevents accumulation of formatting issues
- These standards ensure professional, consistent documentation

**Remember**: The goal is to create clean, readable, and maintainable documentation that follows industry standards while being practical for daily use.
