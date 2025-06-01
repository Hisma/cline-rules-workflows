# Markdown Linting Workflow

## Overview

This workflow provides a systematic approach to implementing and maintaining markdown linting standards across documentation projects. It ensures consistent formatting, quality, and professional presentation.

## When to Use

- Setting up markdown linting for new projects
- Implementing quality standards for existing documentation
- Regular maintenance and validation of markdown content
- Before publishing or releasing documentation
- When onboarding new team members to documentation standards

## Prerequisites

- [ ] Node.js and npm installed
- [ ] Project is under version control (Git)
- [ ] Markdown files exist in the project
- [ ] Write access to project root directory

## Setup Process

### Phase 1: Configuration Setup

**Step 1: Install Markdown Linting Tools**

```bash
# Install markdownlint-cli globally
npm install -g markdownlint-cli

# Or install locally for the project
npm install --save-dev markdownlint-cli
```

**Step 2: Create Linting Configuration**

Create `.markdownlint.json` in project root:

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

**Step 3: Verify Configuration**

```bash
# Test the configuration
markdownlint --config .markdownlint.json README.md
```

### Phase 2: Initial Validation

**Step 4: Run Full Project Scan**

```bash
# Scan all markdown files
markdownlint "**/*.md"

# Save results to file for review
markdownlint "**/*.md" > linting-results.txt
```

**Step 5: Analyze Results**

- [ ] Review all linting errors and warnings
- [ ] Categorize issues by type and severity
- [ ] Identify files requiring immediate attention
- [ ] Plan remediation strategy

**Step 6: Fix Auto-Fixable Issues**

```bash
# Fix issues that can be automatically corrected
markdownlint "**/*.md" --fix

# Review changes before committing
git diff
```

### Phase 3: Manual Remediation

**Step 7: Address Heading Hierarchy Issues (MD001)**

Common fixes:
- Ensure H1 → H2 → H3 progression
- Don't skip heading levels
- Use only one H1 per document

```markdown
# Correct Hierarchy
# Document Title (H1)
## Major Section (H2)
### Subsection (H3)

# Incorrect - Don't Do This
# Document Title (H1)
### Skipped H2 - Wrong!
```

**Step 8: Fix Code Block Language Issues (MD040)**

**Critical**: Every code block must specify a language:

```markdown
# Wrong - No language specified
```
code here
```

# Correct - Language specified
```bash
code here
```
```

**Step 9: Correct List Formatting (MD007)**

Ensure consistent 2-space indentation:

```markdown
# Correct List Formatting
- First item
- Second item
  - Nested item (2 spaces)
  - Another nested item
- Third item
```

**Step 10: Address Other Common Issues**

- **MD003**: Use ATX-style headings (`#` format)
- **MD024**: Ensure unique headings within sections
- **MD033**: Remove or replace disallowed HTML elements
- **MD046**: Use fenced code blocks (```) not indented

### Phase 4: Quality Assurance

**Step 11: Comprehensive Validation**

```bash
# Run final validation
markdownlint "**/*.md"

# Ensure no errors remain
echo $?  # Should return 0 for success
```

**Step 12: Spot Check Critical Files**

- [ ] README.md passes all checks
- [ ] Getting started guides are clean
- [ ] Template files follow standards
- [ ] All code examples have language specifications

**Step 13: Test with Different Tools**

```bash
# Alternative linting tools for comparison
npm install -g remark-cli remark-lint
remark . --use remark-lint
```

### Phase 5: Integration and Automation

**Step 14: Add NPM Scripts**

Add to `package.json`:

```json
{
  "scripts": {
    "lint:md": "markdownlint \"**/*.md\"",
    "lint:md:fix": "markdownlint \"**/*.md\" --fix",
    "lint:md:ci": "markdownlint \"**/*.md\" --config .markdownlint.json"
  }
}
```

**Step 15: Git Hooks Setup**

Create `.git/hooks/pre-commit`:

```bash
#!/bin/sh
# Run markdown linting before commit
npm run lint:md
if [ $? -ne 0 ]; then
  echo "Markdown linting failed. Please fix errors before committing."
  exit 1
fi
```

**Step 16: CI/CD Integration**

Add to GitHub Actions (`.github/workflows/lint.yml`):

```yaml
name: Lint Markdown
on: [push, pull_request]
jobs:
  markdown-lint:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Setup Node.js
        uses: actions/setup-node@v2
        with:
          node-version: '16'
      - name: Install dependencies
        run: npm install -g markdownlint-cli
      - name: Lint markdown files
        run: markdownlint "**/*.md"
```

### Phase 6: Documentation and Training

**Step 17: Create Style Guide**

Document your markdown standards:

```markdown
# Markdown Style Guide

## Code Blocks
- Always specify language: ```bash, ```javascript, ```json
- Use ```text for generic examples
- Use ```markdown for markdown examples

## Headings
- One H1 per document
- Don't skip heading levels
- Use descriptive, clear headings

## Lists
- Use 2-space indentation for nested items
- Be consistent with bullet style (- preferred)
- Use task lists for checklists: - [ ] Item
```

**Step 18: Team Training**

- [ ] Share linting configuration with team
- [ ] Provide examples of common fixes
- [ ] Set up editor integration (VS Code extension)
- [ ] Create quick reference guide

**Step 19: Editor Integration**

**VS Code Setup**:

1. Install "markdownlint" extension
2. Add to `.vscode/settings.json`:

```json
{
  "markdownlint.config": {
    "extends": ".markdownlint.json"
  },
  "editor.codeActionsOnSave": {
    "source.fixAll.markdownlint": true
  }
}
```

## Maintenance Workflow

### Regular Validation

**Weekly Checks**:

```bash
# Quick validation
npm run lint:md

# Check for new issues
markdownlint "**/*.md" --config .markdownlint.json
```

**Monthly Reviews**:

- [ ] Review linting configuration for updates
- [ ] Check for new markdownlint rules
- [ ] Update documentation standards if needed
- [ ] Train new team members

### Handling New Content

**For New Files**:

```bash
# Lint specific file
markdownlint path/to/new-file.md

# Fix issues immediately
markdownlint path/to/new-file.md --fix
```

**For Bulk Updates**:

```bash
# Lint specific directory
markdownlint "docs/**/*.md"

# Fix directory-specific issues
markdownlint "docs/**/*.md" --fix
```

## Troubleshooting

### Common Issues

**MD040 Errors (Missing Code Block Languages)**

```bash
# Find files with unlabeled code blocks
grep -r "^```$" . --include="*.md"
```

Fix by adding appropriate language labels.

**MD001 Errors (Heading Hierarchy)**

```bash
# Find heading structure issues
grep -r "^#" . --include="*.md" | head -20
```

Review and fix heading progression.

**Configuration Not Working**

```bash
# Verify configuration file
cat .markdownlint.json | jq .

# Test with explicit config
markdownlint --config .markdownlint.json README.md
```

### Performance Issues

**Large Projects**:

```bash
# Lint specific directories
markdownlint "docs/**/*.md"
markdownlint "templates/**/*.md"

# Exclude large files if needed
markdownlint "**/*.md" --ignore "node_modules/**"
```

**CI/CD Timeouts**:

- Use caching for node_modules
- Lint only changed files in PRs
- Split linting across multiple jobs

## Quality Metrics

### Success Indicators

- [ ] Zero linting errors across all markdown files
- [ ] Consistent formatting throughout project
- [ ] All code blocks have language specifications
- [ ] Proper heading hierarchy maintained
- [ ] Team follows standards consistently

### Monitoring

```bash
# Generate linting report
markdownlint "**/*.md" --output linting-report.json

# Count total issues
markdownlint "**/*.md" | wc -l
```

## Best Practices

### Configuration Management

- Keep `.markdownlint.json` in version control
- Document any custom rule modifications
- Share configuration across team projects
- Regular review and updates

### Team Adoption

- Provide clear examples of correct formatting
- Set up editor integration for immediate feedback
- Include linting in code review process
- Celebrate improvements in documentation quality

### Continuous Improvement

- Monitor for new markdownlint features
- Gather team feedback on rules
- Adjust configuration based on project needs
- Share learnings across projects

## Notes

- This workflow ensures professional, consistent documentation
- Automation reduces manual review burden
- Editor integration provides immediate feedback
- Regular maintenance keeps standards current
- Team training ensures consistent adoption

**Remember**: The goal is to create clean, readable, and maintainable documentation that follows industry standards while being practical for daily use.
