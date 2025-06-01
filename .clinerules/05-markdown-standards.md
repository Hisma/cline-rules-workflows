# Markdown Standards

## Overview

Keep markdown simple, readable, and natural. Focus on content clarity over rigid structure.

## Essential Rules

### 1. Code Blocks Must Have Languages

**CRITICAL**: Every fenced code block MUST specify a language:

```bash
# Good - has language specified
npm install
```

```text
# Bad - no language specified
npm install
```

### 2. Use Natural Structure

- **Headings** - For actual document sections, not examples or lists
- **Bullet points** - For lists, options, examples, and features
- **Ordered lists** - ONLY for step-by-step procedures where order matters
- **Code blocks** - For commands, code, and file contents
- **Regular text** - For explanations and descriptions

### 3. Keep It Simple

- Use headings to organize document sections, not to highlight every piece of content
- Use bullet points for lists of items, alternatives, examples, or features
- Use numbered lists ONLY for actual step-by-step procedures
- Don't over-structure - if it reads naturally, it's probably right
- Structure should serve content, not dominate it

## Common Language Tags

- `bash` - Shell commands
- `json` - JSON configuration
- `yaml` - YAML files
- `javascript` - JavaScript code
- `text` - Generic text or examples
- `tree` - Directory structures

## What NOT to Do

### ❌ Don't Make Everything a Heading

```text
# Wrong - these should be bullet points
# Option 1: Do this
# Option 2: Do that
# Option 3: Do something else
```

### ✅ Use Bullet Points for Lists

- Option 1: Do this
- Option 2: Do that  
- Option 3: Do something else

### ❌ Don't Wrap Markdown in Markdown

```markdown
# This is wrong - markdown in markdown blocks
- List item
```

### ✅ Use Appropriate Language Tags

```text
# This is correct - text language for examples
- List item
```

## Linting Configuration

The `.markdownlint.json` file enforces these standards:

```json
{
  "MD003": {
    "style": "atx"
  },
  "MD007": {
    "indent": 2
  },
  "MD013": false,
  "MD024": false,
  "MD025": {
    "front_matter_title": "^\\s*title\\s*[:=]"
  },
  "MD026": false,
  "MD033": {
    "allowed_elements": ["br", "details", "summary", "img", "kbd", "sub", "sup"]
  },
  "MD036": false,
  "MD041": false,
  "MD046": {
    "style": "fenced"
  },
  "MD048": {
    "style": "backtick"
  }
}
```

## When to Use Ordered Lists vs Bullet Points

**Use bullet points for:**

- Lists of features or options
- Examples and alternatives  
- Non-sequential items
- Anything where order doesn't matter

**Use numbered lists only for:**

- Step-by-step procedures
- Sequential instructions
- Processes where order matters
- Actual workflows with dependencies

## How to Find Missing Language Tags

**Use markdownlint - it does all the work for you:**

```bash
# Step 1: Run markdownlint to find violations
markdownlint "**/*.md"
```

Look for `MD040/fenced-code-language` violations in the output:

```text
file.md:32 MD040/fenced-code-language Fenced code blocks should have a language specified
file.md:45 MD040/fenced-code-language Fenced code blocks should have a language specified
```

**Step 2: Go to those specific line numbers and add language tags**

**Step 3: Run markdownlint again to verify fixes**

### ❌ Don't Do This

- Don't use complex grep patterns to find opening vs closing fences
- Don't try to parse markdown structure manually  
- Don't overcomplicate it with pair-based detection

### ✅ Do This

1. Run `markdownlint "**/*.md"`
2. Fix the specific line numbers it identifies
3. Run markdownlint again to confirm

**That's it!** Markdownlint already knows which fences need language tags.

## Quick Check

Before saving any markdown file, ask:

- Do all code blocks have language tags?
- Are headings used for document structure (not examples)?
- Are numbered lists only used for actual step-by-step procedures?
- Are bullet points used for features, options, and examples?
- Is the content easy to read?

**Remember**: Markdown should feel natural. If you're fighting with the formatting, you're probably overcomplicating it.
