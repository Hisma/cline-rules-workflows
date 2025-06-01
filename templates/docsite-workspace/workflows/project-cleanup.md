# Project Cleanup Workflow

## Overview

This workflow provides a systematic approach to cleaning up and organizing documentation projects. It ensures consistency, removes outdated content, and maintains high-quality standards.

## When to Use

- Before major releases or milestones
- Monthly maintenance cycles
- After significant content restructuring
- When preparing for community contributions
- Before archiving or transferring projects

## Prerequisites

- [ ] Project is under version control (Git)
- [ ] MCP servers are configured (Brave Search, Puppeteer)
- [ ] Markdown linting is set up (`.markdownlint.json` exists)
- [ ] Backup of current state is available

## Cleanup Process

### Phase 1: Content Audit

**Step 1: Review Documentation Structure**

```bash
# Generate current file structure
find . -name "*.md" -type f | sort > current-structure.txt
```

- [ ] Review all markdown files for relevance
- [ ] Identify outdated or duplicate content
- [ ] Check for broken internal links
- [ ] Verify template compliance

**Step 2: Link Validation**

```bash
# Install and run link checker
npm install -g markdown-link-check
find . -name "*.md" -exec markdown-link-check {} \;
```

- [ ] Fix broken external links
- [ ] Update outdated references
- [ ] Remove or replace dead links
- [ ] Verify internal cross-references

**Step 3: Content Currency Check**

Using MCP servers to verify information:

- [ ] Use Brave Search to verify current best practices
- [ ] Check official documentation for updates
- [ ] Validate code examples and configurations
- [ ] Update version numbers and compatibility information

### Phase 2: Quality Assurance

**Step 4: Markdown Linting**

```bash
# Run markdown linting
markdownlint "**/*.md"

# Fix auto-fixable issues
markdownlint "**/*.md" --fix
```

- [ ] Fix all linting errors
- [ ] Ensure consistent formatting
- [ ] Verify code block language specifications
- [ ] Check heading hierarchy

**Step 5: Content Standards Review**

- [ ] Verify all placeholders are properly formatted (`[Description]`)
- [ ] Check for consistent terminology usage
- [ ] Ensure proper citation of sources
- [ ] Validate template compliance

**Step 6: Accessibility and Readability**

- [ ] Check heading structure for logical flow
- [ ] Verify alt text for images
- [ ] Ensure clear, actionable language
- [ ] Test navigation paths

### Phase 3: Organization and Structure

**Step 7: File Organization**

```bash
# Check directory structure
tree -I 'node_modules|.git' > directory-structure.txt
```

- [ ] Verify proper directory structure
- [ ] Move misplaced files to correct locations
- [ ] Update file naming for consistency
- [ ] Remove empty or unnecessary directories

**Step 8: Template Alignment**

- [ ] Ensure all rules follow template structure
- [ ] Verify workflow files are properly organized
- [ ] Check that examples match current templates
- [ ] Update cross-references between files

**Step 9: Documentation Updates**

- [ ] Update README with current information
- [ ] Refresh getting started guides
- [ ] Verify setup instructions are current
- [ ] Update any changed file paths or references

### Phase 4: Final Validation

**Step 10: Comprehensive Testing**

```bash
# Final markdown validation
markdownlint "**/*.md"

# Check for any remaining issues
grep -r "TODO\|FIXME\|XXX" . --include="*.md"
```

- [ ] All markdown files pass linting
- [ ] No TODO or FIXME comments remain
- [ ] All links are functional
- [ ] Templates work as documented

**Step 11: Version Control Cleanup**

```bash
# Review git status
git status

# Stage all changes
git add .

# Commit cleanup changes
git commit -m "Project cleanup: update documentation, fix links, improve organization"
```

- [ ] Commit all cleanup changes
- [ ] Tag release if appropriate
- [ ] Update changelog if maintained
- [ ] Push changes to remote repository

## Quality Checklist

### Content Quality

- [ ] All information is current and accurate
- [ ] Examples work as documented
- [ ] Links are functional and relevant
- [ ] Language is clear and actionable

### Technical Quality

- [ ] All markdown files pass linting
- [ ] Code blocks specify appropriate languages
- [ ] Heading hierarchy is logical
- [ ] File organization follows templates

### User Experience

- [ ] Navigation is intuitive
- [ ] Getting started path is clear
- [ ] Examples are practical and useful
- [ ] Documentation serves target users effectively

## Post-Cleanup Actions

### Documentation

- [ ] Update project status in overview
- [ ] Refresh last-updated dates
- [ ] Document any structural changes
- [ ] Update contributor guidelines if needed

### Communication

- [ ] Notify team of cleanup completion
- [ ] Share any significant changes
- [ ] Update project roadmap if affected
- [ ] Prepare release notes if applicable

### Monitoring

- [ ] Set up regular cleanup schedule
- [ ] Monitor for new issues or outdated content
- [ ] Track user feedback on improvements
- [ ] Plan next cleanup cycle

## Troubleshooting

### Common Issues

**Broken Links**
- Check if target moved or was renamed
- Update internal references
- Replace with current alternatives
- Remove if no longer relevant

**Linting Errors**
- Review markdown standards rule
- Fix heading hierarchy issues
- Add language specifications to code blocks
- Correct list formatting

**Outdated Content**
- Use MCP servers to verify current information
- Check official documentation for updates
- Update examples and configurations
- Remove deprecated features

**Template Misalignment**
- Review current template structure
- Update files to match templates
- Fix cross-references and links
- Ensure consistent organization

## Success Metrics

- [ ] Zero markdown linting errors
- [ ] All links functional
- [ ] Content verified as current
- [ ] Template compliance achieved
- [ ] User feedback positive
- [ ] Navigation improved

## Notes

- This workflow should be run regularly to maintain quality
- Use MCP servers for fact-checking and verification
- Document any significant changes for team awareness
- Consider automation for routine checks
- Maintain backup before major cleanup operations

**Remember**: The goal is to maintain high-quality, current, and useful documentation that serves users effectively.
