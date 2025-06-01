# Creating Custom Workflows

This guide walks you through creating your own custom Cline workflows, from simple automation to complex multi-step processes.

## Understanding Workflow Basics

Workflows are markdown files that provide step-by-step instructions for Cline to follow. They're invoked using slash commands and can range from simple checklists to complex automation sequences.

### Key Concepts

- **Workflows are executable** - Unlike rules (which provide context), workflows are action-oriented
- **Invoked on-demand** - Use `/workflow-name.md` to trigger them
- **Step-by-step guidance** - Break complex tasks into manageable steps
- **Context-aware** - Can reference project rules and current state

## Your First Custom Workflow

Let's create a simple workflow to get started:

### Example: Code Cleanup Workflow

## Code Cleanup Workflow

This workflow helps clean up and organize code before committing.

## Prerequisites
- Working directory is clean (no uncommitted changes)
- All dependencies installed
- Linting tools configured

## Steps

1. **Format Code**
   - Run code formatter: `npm run format` or equivalent
   - Verify no formatting errors
   - Check that files were actually formatted

2. **Run Linter**
   - Execute linter: `npm run lint`
   - Fix any linting errors found
   - Re-run linter to confirm all issues resolved

3. **Remove Unused Imports**
   - Check for unused imports in modified files
   - Remove any imports that aren't being used
   - Verify code still compiles after removal

4. **Update Documentation**
   - Check if any function signatures changed
   - Update JSDoc/comments if needed
   - Verify README is still accurate

5. **Final Verification**
   - Run tests to ensure nothing broke: `npm test`
   - Build project to check for issues: `npm run build`
   - Review changes before committing

## Success Criteria
- All linting passes
- Tests pass
- Build succeeds
- Code is properly formatted

## Workflow Structure Patterns

### Basic Structure

Every workflow should have these core elements:

## Workflow Title

Brief description of what this workflow does.

## Prerequisites
- What needs to be ready before starting

## Steps
1. **Step Name**
   - Specific actions to take
   - How to verify success

## Success Criteria
- How to know the workflow completed successfully

### Advanced Structure

For more complex workflows, consider adding:

## Advanced Workflow Title

Detailed description and when to use this workflow.

## Prerequisites
- Required tools and setup
- Environmental requirements
- Access permissions needed

## Overview
- High-level summary of what will happen
- Estimated time to complete
- Any risks or considerations

## Steps

### Phase 1: Preparation
1. **Step 1**
   - Actions
   - Verification
   - Troubleshooting

### Phase 2: Execution
- **Step 2**
  - Actions
  - Expected results
  - Error handling

### Phase 3: Verification
- **Step 3**
  - Validation steps
  - Success indicators

## Troubleshooting
### Common Issue 1
- Symptoms
- Solution

## Rollback Procedure
- How to undo changes if something goes wrong

## Success Criteria
- Detailed success indicators
- What should be different after completion

## Workflow Types and Examples

### 1. Development Workflows

**Code Review Workflow:**

## Code Review Workflow

### Steps
1. **Analyze Changes**
   - Review git diff: `git diff main...feature-branch`
   - Identify modified files and their purposes
   - Check for breaking changes

2. **Quality Assessment**
   - Verify coding standards compliance
   - Check for proper error handling
   - Ensure adequate test coverage

3. **Security Review**
   - Look for potential vulnerabilities
   - Verify input validation
   - Check for sensitive data exposure

4. **Provide Feedback**
   - Document specific issues found
   - Suggest improvements
   - Approve or request changes

**Dependency Update Workflow:**

## Update Dependencies Workflow

## Steps
1. **Check Current State**
   - Review current dependencies: `npm list --depth=0`
   - Check for security vulnerabilities: `npm audit`
   - Note any deprecated packages

2. **Update Dependencies**
   - Update patch versions: `npm update`
   - Check for major version updates: `npm outdated`
   - Update major versions one at a time

3. **Test After Updates**
   - Run full test suite: `npm test`
   - Check for breaking changes
   - Test critical functionality manually

4. **Document Changes**
   - Update CHANGELOG.md
   - Note any breaking changes
   - Commit dependency updates

### 2. Deployment Workflows

**Production Deployment:**

## Deploy to Production Workflow

## Prerequisites
- All tests passing
- Code reviewed and approved
- Staging deployment successful
- Deployment window scheduled

## Steps
1. **Pre-deployment Checks**
   - Verify staging environment matches production
   - Check database migration status
   - Confirm backup completed

2. **Deploy Application**
   - Deploy to production servers
   - Run database migrations if needed
   - Update configuration files

3. **Post-deployment Verification**
   - Run smoke tests
   - Check application logs
   - Verify key functionality works

4. **Monitor and Document**
   - Monitor error rates for 30 minutes
   - Update deployment log
   - Notify stakeholders of completion

### 3. Maintenance Workflows

**Rules and Workflows Maintenance:**

## Update Rules & Workflows Workflow

## Steps
1. **Project Assessment**
   - Review project structure and recent changes
   - Identify what has evolved since rules were last updated
   - Note new requirements or constraints

2. **Rules Alignment Review**
   - Update all files in .clinerules/ to reflect current reality
   - Refresh technical information and priorities
   - Ensure project descriptions match current state

3. **Workflow Updates**
   - Review and update workflows as needed
   - Fix outdated procedures and tool references
   - Verify workflows align with current processes

**Database Maintenance:**

## Database Maintenance Workflow

## Steps
1. **Backup Database**
   - Create full database backup
   - Verify backup integrity
   - Store backup in secure location

2. **Analyze Performance**
   - Check slow query log
   - Analyze table sizes and indexes
   - Identify optimization opportunities

3. **Perform Maintenance**
   - Update table statistics
   - Rebuild fragmented indexes
   - Clean up old log files

4. **Verify Health**
   - Run database health checks
   - Test critical queries
   - Monitor performance metrics

## Advanced Workflow Techniques

### Conditional Logic

Handle different scenarios within workflows:

## Steps

1. **Determine Environment**
   - Check current git branch: `git branch --show-current`
   - **If branch is 'main':**
     - Use production configuration
     - Require additional approvals
   - **If branch is 'develop':**
     - Use staging configuration
     - Skip approval requirements
   - **Otherwise:**
     - Use development configuration
     - Enable debug mode

2. **Environment-Specific Actions**
   - Configure based on environment determined above
   - Apply appropriate security settings
   - Set correct API endpoints

### Workflow Composition

Reference other workflows to build complex processes:

## Steps

1. **Pre-release Preparation**
   - Run code review workflow: `/code-review.md`
   - Execute test suite workflow: `/run-full-tests.md`
   - Verify all checks pass before proceeding

2. **Release Process**
   - Run deployment workflow: `/deploy-production.md`
   - Execute post-deployment workflow: `/verify-deployment.md`
   - Document release completion

### Error Handling and Recovery

Include robust error handling:

- **Deploy Application**
  - Execute deployment script: `./deploy.sh production`
  - Monitor deployment progress
  - **If deployment fails:**
    - Check deployment logs: `tail -f /var/log/deploy.log`
    - Verify server connectivity: `ping production-server.com`
    - **If critical failure:**
      - Execute rollback: `/rollback-deployment.md`
      - Notify incident response team
      - Document failure for post-mortem
    - **If minor failure:**
      - Retry deployment with fixes
      - Continue monitoring

## Testing Your Workflows

### Dry Run Testing

1. **Manual Walkthrough**
   - Follow each step manually without Cline
   - Note any unclear or missing instructions
   - Time how long each step takes
   - Document any issues encountered

- **Cline Testing**
  - Invoke workflow with `/workflow-name.md`
  - Observe how Cline interprets each step
  - Note any confusion or misinterpretation
  - Refine instructions based on results

### Validation Checklist

- [ ] Prerequisites are clearly stated
- [ ] Each step is actionable and specific
- [ ] Success criteria are measurable
- [ ] Error handling is included
- [ ] Workflow can be completed start to finish
- [ ] Instructions are clear to someone unfamiliar with the process

## Workflow Maintenance

### Regular Updates

**Monthly Review:**

- Check if workflows are still relevant
- Update any changed commands or URLs
- Remove workflows that are no longer used
- Add new workflows for emerging processes

**After Tool Changes:**

- Update workflows when development tools change
- Modify commands if CLI interfaces change
- Test workflows in new environments
- Update prerequisites if requirements change

### Version Control

Track workflow evolution:

## Workflow Name

<!-- 
Version: 2.1
Last Updated: 2024-01-15
Changelog:
- v2.1: Added error handling for network failures
- v2.0: Updated to use new deployment tool
- v1.0: Initial version
-->

## Integration with Rules

Workflows work best when combined with rules:

### Rules Inform Workflows

Rules provide context that workflows can reference:

**Rule (in coding-standards.md):**

## Testing Standards
- Minimum 80% code coverage required
- All tests must pass before deployment
- Integration tests required for API changes

**Workflow (in deploy-staging.md):**

1. **Verify Test Requirements**
   - Run coverage report: `npm run coverage`
   - Ensure coverage meets project standard (check coding-standards.md)
   - Verify all tests pass: `npm test`
   - Run integration tests if API changed

### Workflows Enforce Rules

Workflows can ensure rules are followed:

- **Code Quality Check**
  - Verify code follows project standards (see coding-standards.md)
  - Check for proper error handling
  - Ensure documentation is updated
  - Validate security requirements are met

## Common Pitfalls and Solutions

### Overly Complex Workflows

**Problem:** Workflows try to do too much
**Solution:** Break into smaller, focused workflows

**Instead of:**
- Deploy, Test, and Document Everything Workflow

**Use:**
- Deploy to Staging Workflow
- Run Integration Tests Workflow  
- Update Documentation Workflow

### Vague Instructions

**Problem:** Steps are too general
**Solution:** Be specific about commands and expected outcomes

**Instead of:**

- **Test the application**
  - Make sure everything works

**Use:**

- **Run Test Suite**
  - Execute: `npm test`
  - Verify: All tests pass (0 failures)
  - Check: Coverage above 80%

### Missing Error Handling

**Problem:** No guidance when things go wrong
**Solution:** Include troubleshooting and recovery steps

- **Build Application**
  - Run: `npm run build`
  - **If build fails:**
    - Check for TypeScript errors
    - Verify all dependencies installed
    - Clear cache: `npm run clean`
    - Retry build

## Best Practices Summary

1. **Start Simple** - Begin with basic workflows and add complexity gradually
2. **Be Specific** - Use exact commands and clear success criteria
3. **Include Context** - Reference relevant rules and project standards
4. **Handle Errors** - Provide guidance for when things go wrong
5. **Test Thoroughly** - Validate workflows work as expected
6. **Maintain Regularly** - Keep workflows current and relevant
7. **Document Changes** - Track workflow evolution over time
8. **Focus on Value** - Only create workflows that solve real problems

## Getting Started

1. **Identify a Process** - Choose a task you do repeatedly
2. **Write It Down** - Document the steps you currently follow
3. **Create the Workflow** - Convert your notes into a workflow file
4. **Test It** - Use the workflow and refine based on experience
5. **Iterate** - Improve the workflow based on real usage

Remember: The best workflows are ones you actually use. Start with processes that cause you friction and build from there.
