# Markdown Linting Workflow

## Overview

This workflow guides you through running markdown linting on this documentation project. It checks if the necessary tools are installed, sets them up if needed, then executes linting to ensure all markdown files meet quality standards.

## When to Use

- Before committing changes to documentation
- After adding new markdown files
- During regular quality maintenance
- When preparing for documentation releases
- To validate template consistency

## Prerequisites

- [ ] Node.js and npm installed
- [ ] Project is under version control (Git)
- [ ] Write access to project directory

## Step 1: Check Environment Setup

**Check if markdownlint-cli is installed:**

```bash
# Check if markdownlint is available
which markdownlint
# or
markdownlint --version
```

**If not installed, install it:**

```bash
# Install globally (recommended)
npm install -g markdownlint-cli

# Or install locally for this project
npm install --save-dev markdownlint-cli
```

**Verify .markdownlint.json exists:**

```bash
# Check if configuration file exists
ls -la .markdownlint.json
```

**If configuration is missing, create it:**

```bash
# Create the configuration file
cat > .markdownlint.json << 'EOF'
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
EOF
```

## Step 2: Run Initial Linting Scan

**Scan all markdown files in the project:**

```bash
# Run linting on all markdown files
markdownlint "**/*.md"
```

**For detailed output with line numbers:**

```bash
# Get detailed linting results
markdownlint "**/*.md" --config .markdownlint.json
```

**Save results for analysis:**

```bash
# Save linting results to file
markdownlint "**/*.md" > linting-results.txt 2>&1
cat linting-results.txt
```

## Step 3: Fix Auto-Correctable Issues

**Apply automatic fixes:**

```bash
# Fix issues that can be automatically corrected
markdownlint "**/*.md" --fix

# Review what was changed
git diff
```

**Check specific directories:**

```bash
# Lint specific areas of the project
markdownlint "docs/**/*.md" --fix
markdownlint "templates/**/*.md" --fix
markdownlint ".clinerules/**/*.md" --fix
```

## Step 4: Address Manual Fixes

**Common issues to fix manually:**

### MD040 - Code Block Language Missing

Find unlabeled code blocks:

```bash
# Find code blocks without language specification
grep -r "^```$" . --include="*.md"
```

**Fix by adding language labels:**

- **Wrong**
<!-- markdownlint-disable MD040 -->
```
code here
```
<!-- markdownlint-enable MD040 -->

- **Correct**

```bash
code here
```

### MD001 - Heading Hierarchy

Check heading structure:

```bash
# Review heading hierarchy
grep -r "^#" . --include="*.md" | head -20
```

**Ensure proper progression:**

```text
# Document Title (H1)
## Major Section (H2)
### Subsection (H3)
#### Details (H4)
```

### MD024 - Duplicate Headings

**Fix duplicate headings in same section:**

```text
# Use unique headings or add context
## Setup Process
## Setup Process for Development  # Better

# Or use different heading levels
## Setup
### Setup for Production
### Setup for Development
```

## Step 5: Validate Specific File Types

**Check critical project files:**

```bash
# Validate key files
markdownlint README.md
markdownlint docs/getting-started.md
markdownlint .clinerules/*.md
```

**Check template files:**

```bash
# Validate all templates
markdownlint templates/global/Rules/*.md
markdownlint templates/global/Workflows/*.md
markdownlint templates/docsite-workspace/**/*.md
markdownlint templates/web-app-workspace/**/*.md
```

## Step 6: Final Validation

**Run comprehensive check:**

```bash
# Final validation of all files
markdownlint "**/*.md"

# Verify exit code (0 = success)
echo "Exit code: $?"
```

**Spot check critical areas:**

- [ ] README.md passes all checks
- [ ] All documentation in docs/ is clean
- [ ] Template files follow standards
- [ ] .clinerules/ files are properly formatted
- [ ] All code examples have language specifications

## Step 7: Project-Specific Validation

**Check project structure compliance:**

```bash
# Validate that all markdown files exist where expected
find . -name "*.md" -type f | sort
```

**Verify template consistency:**

```bash
# Check that templates follow naming conventions
ls -la templates/*/rules/
ls -la templates/*/workflows/
```

**Validate internal links:**

```bash
# Check for broken internal links (basic check)
grep -r "\[.*\](.*\.md)" . --include="*.md" | grep -v "http"
```

## Troubleshooting

### Common Project-Specific Issues

**Configuration not found:**

```bash
# Verify you're in the project root
pwd
ls -la .markdownlint.json
```

**Permission issues:**

```bash
# Check file permissions
ls -la .markdownlint.json
chmod 644 .markdownlint.json
```

**Large number of errors:**

```bash
# Focus on specific directories first
markdownlint "docs/**/*.md"
markdownlint "templates/global/**/*.md"
```

### Performance for Large Projects

**Lint specific areas:**

```bash
# Process in chunks
markdownlint "docs/**/*.md"
markdownlint "templates/**/*.md"
markdownlint ".clinerules/**/*.md"
```

**Exclude unnecessary files:**

```bash
# Skip node_modules and other directories
markdownlint "**/*.md" --ignore "node_modules/**" --ignore ".git/**"
```

## Maintenance Commands

**Quick daily check:**

```bash
# Fast validation
markdownlint "**/*.md" --config .markdownlint.json
```

**Before committing:**

```bash
# Pre-commit validation
markdownlint "**/*.md" && echo "✅ All markdown files pass linting"
```

**After adding new files:**

```bash
# Check only recently modified files
git diff --name-only HEAD~1 | grep "\.md$" | xargs markdownlint
```

## Success Criteria

- [ ] All markdown files pass linting without errors
- [ ] Code blocks have appropriate language specifications
- [ ] Heading hierarchy is consistent throughout project
- [ ] Template files maintain consistent formatting
- [ ] Documentation follows project standards
- [ ] No broken internal references

## Integration with Development Workflow

**Add to package.json (if using npm):**

```json
{
  "scripts": {
    "lint:md": "markdownlint \"**/*.md\"",
    "lint:md:fix": "markdownlint \"**/*.md\" --fix"
  }
}
```

**Pre-commit hook:**

```bash
# Add to .git/hooks/pre-commit
#!/bin/sh
markdownlint "**/*.md"
if [ $? -ne 0 ]; then
  echo "❌ Markdown linting failed. Please fix errors before committing."
  exit 1
fi
echo "✅ Markdown linting passed"
```

## Notes

- This workflow assumes the project already has markdown files to lint
- The .markdownlint.json configuration is optimized for documentation projects
- Focus on MD040 (code block languages) as it's the most critical rule
- Regular linting prevents accumulation of formatting issues
- Template files should maintain the highest quality standards

**Remember**: The goal is to ensure all documentation meets professional standards and maintains consistency across the entire project.
