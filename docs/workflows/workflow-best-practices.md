# Workflow Best Practices

This guide covers best practices for creating, organizing, and maintaining effective Cline workflows. These are example patterns and suggestions - adapt them to fit your specific needs and development style.

## Workflow Design Principles

### 1. Single Responsibility

Each workflow should handle one specific process or task:

**✅ Good:**

- `deploy-staging.md` - Handles staging deployment only
- `code-review.md` - Focuses on code review process
- `setup-testing.md` - Sets up testing infrastructure

**❌ Avoid:**

- `deploy-and-test-and-review.md` - Too many responsibilities
- `general-development.md` - Too broad and unfocused

### 2. Clear and Actionable Steps

Every step should be specific and executable:

**✅ Good:**

1. **Run Test Suite**
   - Execute `npm test` in project root
   - Verify all tests pass (0 failures)
   - Check test coverage is above 80%

**❌ Avoid:**

1. **Test Everything**
   - Make sure tests work
   - Check coverage

### 3. Include Prerequisites

Always specify what needs to be ready before starting:

## Prerequisites
- Node.js 18+ installed
- All dependencies installed (`npm install`)
- Database running on localhost:5432
- Environment variables configured

### 4. Add Verification Steps

Include checks to ensure each step completed successfully:

- **Build Application**
  - Run `npm run build`
  - Verify build directory created
  - Check for build errors in output
  - Confirm bundle size is reasonable

## Workflow Organization

### Global vs Project Workflows

**Global Workflows** (`~/Documents/Cline/.clinerules/workflows/`):

- Reusable across all projects
- Technology-agnostic processes
- General development practices

Examples:

- `code-review.md`
- `security-audit.md`
- `documentation-update.md`
- `dependency-update.md`

**Project Workflows** (`.clinerules/workflows/`):

- Specific to the current project
- Use project-specific tools and configurations
- Handle unique deployment or testing scenarios

Examples:

- `deploy-production.md`
- `run-integration-tests.md`
- `update-api-docs.md`
- `migrate-database.md`

### Naming Conventions

Use descriptive, action-oriented names:

**✅ Good Names:**

- `deploy-staging.md`
- `run-security-scan.md`
- `update-dependencies.md`
- `generate-api-docs.md`

**❌ Avoid:**

- `workflow1.md`
- `stuff.md`
- `deploy.md` (too generic)
- `the-deployment-workflow-for-staging.md` (too verbose)

### File Organization

One approach is to organize workflows by category when you have many:

```tree
.clinerules/workflows/
├── deployment/
│   ├── deploy-staging.md
│   ├── deploy-production.md
│   └── rollback.md
├── testing/
│   ├── run-unit-tests.md
│   ├── run-integration-tests.md
│   └── performance-test.md
└── maintenance/
    ├── update-dependencies.md
    ├── cleanup-logs.md
    └── backup-database.md
```
*Note: This is just one organizational pattern. You might prefer a flat structure or organize by frequency of use.*

## Writing Effective Workflows

### Example Structure Template

Here's one pattern you can use for consistent workflow structure:

```text
# Workflow Name

Brief description of what this workflow accomplishes.

## Prerequisites
- List what needs to be ready
- Include required tools or access
- Specify environment requirements

## Steps

1. **Step Name**
   - Specific action to take
   - Expected outcome
   - Verification method

2. **Next Step**
   - Another specific action
   - How to confirm success
   - What to do if it fails

## Troubleshooting

### Common Issue 1
- Symptoms: What you might see
- Solution: How to fix it

### Common Issue 2
- Symptoms: What indicates this problem
- Solution: Steps to resolve

## Success Criteria
- How to know the workflow completed successfully
- What should be different after completion
```

*This is just one template approach - feel free to adapt or create your own structure that works better for your needs.*

### Language and Tone

**Use Active Voice:**

- ✅ "Run the test suite"
- ❌ "The test suite should be run"

**Be Specific:**

- ✅ "Execute `npm run build:production`"
- ❌ "Build the app"

**Include Context:**

- ✅ "Deploy to staging server (staging.example.com)"
- ❌ "Deploy to staging"

### Error Handling

Consider including guidance for when things go wrong:

- **Deploy Application**
  - Run deployment script: `./scripts/deploy.sh staging`
  - Monitor deployment logs for errors
  - **If deployment fails:**
    - Check server connectivity: `ping staging.example.com`
    - Verify credentials are current
    - Review deployment logs in `/var/log/deploy.log`
    - Consider rolling back: `./scripts/rollback.sh`

## Workflow Maintenance

### Regular Review

Consider scheduling periodic reviews of your workflows:

**Monthly:**

- Check if workflows are still being used
- Update any outdated commands or URLs
- Remove workflows that are no longer relevant

**After Major Changes:**

- Update workflows when tools or processes change
- Test workflows in new environments
- Update prerequisites if dependencies change

### Version Control

One approach is to track workflow changes:

```text
# Deploy to Production

Last updated: 2024-01-15
Version: 2.1

## Changelog
- v2.1: Added health check verification step
- v2.0: Updated to use new deployment tool
- v1.0: Initial version
```

### Testing Workflows

Regularly test your workflows:

1. **Dry Run Testing**
   - Follow workflow steps manually
   - Note any unclear or outdated instructions
   - Time how long each step takes

- **Usage Testing**
  - Use workflows in real scenarios
  - Collect feedback on clarity and completeness
  - Update based on actual usage patterns

## Advanced Patterns

### Conditional Logic

Handle different scenarios within workflows:

- **Determine Deployment Target**
  - Check current branch: `git branch --show-current`
  - **If branch is 'main':**
    - Deploy to production environment
    - Require manual approval before proceeding
  - **If branch is 'develop':**
    - Deploy to staging environment
    - Run full test suite first
  - **Otherwise:**
    - Deploy to development environment
    - Skip approval requirements

### Workflow Dependencies

Reference other workflows when appropriate:

1. **Pre-deployment Setup**
   - First, run the code review workflow: `/code-review.md`
   - Ensure all tests pass: `/run-full-test-suite.md`
   - Only proceed if both workflows complete successfully

### Environment-Specific Workflows

Create variations for different environments:

```tree
workflows/
├── deploy-development.md
├── deploy-staging.md
└── deploy-production.md
```

Each with environment-specific steps and requirements.

## Common Workflow Patterns

These are example patterns you might find useful:

### Deployment Workflow Pattern

```text
# Deploy to [Environment]

## Prerequisites
- Code reviewed and approved
- All tests passing
- [Environment] server accessible

## Steps
1. **Pre-deployment Checks**
2. **Build Application**
3. **Deploy to Server**
4. **Post-deployment Verification**
5. **Notification and Documentation**
```

### Testing Workflow Pattern

```text
# Run [Test Type] Tests

## Prerequisites
- Test environment configured
- Test data available
- Dependencies installed

## Steps
1. **Setup Test Environment**
2. **Execute Tests**
3. **Analyze Results**
4. **Generate Reports**
5. **Cleanup**
```

### Maintenance Workflow Pattern

```text
# [Maintenance Task]

## Prerequisites
- Backup completed
- Maintenance window scheduled
- Stakeholders notified

## Steps
1. **Preparation**
2. **Execute Maintenance**
3. **Verification**
4. **Cleanup and Documentation**
```

### Rules and Workflows Maintenance Pattern

```text
# Update Rules & Workflows

## Prerequisites
- Project has existing .clinerules/ directory
- Understanding of current project state
- MCP servers configured for research

## Steps
1. **Project Assessment**
2. **Rules Alignment Review**
3. **Workflow Updates**
```

*Example: The `update-rules-workflows.md` global workflow follows this pattern to help keep project rules and workflows aligned with evolving project reality.*
## Integration with Rules

Workflows work well when combined with rules:

### Rules Provide Context

Rules help workflows understand:

- Project coding standards
- Security requirements
- Documentation expectations
- Quality thresholds

### Workflows Provide Process

Workflows give step-by-step guidance for:

- Complex multi-step tasks
- Deployment procedures
- Testing protocols
- Maintenance routines

### Example Integration

**Rule (coding-standards.md):**

## Testing Requirements
- Minimum 80% code coverage
- All tests must pass before deployment
- Integration tests required for API changes

**Workflow (deploy-staging.md):**

1. **Verify Test Coverage**
   - Run coverage report: `npm run coverage`
   - Ensure coverage meets project standard (80%+)
   - All tests must pass (0 failures)

## Troubleshooting Common Issues

### Workflows Not Executing

**Problem:** Workflow doesn't start when invoked
**Solutions:**

- Check file location and naming
- Verify `.md` extension
- Ensure proper directory structure
- Restart VSCode if needed

### Unclear Instructions

**Problem:** Workflow steps are hard to follow
**Solutions:**

- Add more specific commands
- Include expected outputs
- Add troubleshooting sections
- Test with fresh perspective

### Outdated Workflows

**Problem:** Workflows reference old tools or processes
**Solutions:**

- Schedule regular review cycles
- Update after major project changes
- Version control workflow files
- Document change history

## Success Indicators

Consider tracking workflow effectiveness:

### Usage Patterns

- Which workflows are used most frequently
- Which workflows are never used (candidates for removal)
- How often workflows need modification

### Quality Indicators

- Reduction in process errors
- Faster task completion
- Improved consistency in your work
- Fewer issues with complex tasks

### Personal Feedback

- Note which workflows save you time
- Identify workflows that need improvement
- Track which processes become more reliable
- Monitor your own adoption patterns

## Customization Guidelines

Remember that these are example patterns and suggestions:

- **Adapt to your style** - Modify templates and structures to fit your preferences
- **Start simple** - Begin with basic workflows and add complexity as needed
- **Iterate based on use** - Refine workflows based on real usage
- **Focus on value** - Only create workflows that actually help your development process

The best workflow system is one that fits your specific needs and development style. Use these patterns as a starting point, but don't hesitate to create your own approaches that work better for your situation.
