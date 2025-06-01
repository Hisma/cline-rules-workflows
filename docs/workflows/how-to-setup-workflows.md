# How to Setup Cline Workflows

This guide walks you through setting up your own Cline workflows system, covering both global and project-specific workflows.

## Prerequisites

- Cline VSCode extension installed (v3.17+ for workflows support)
- MCP servers configured (essential for research-driven workflows)
- Basic understanding of Markdown
- Familiarity with your development processes
- Understanding of workflow automation concepts

### MCP Server Setup (Essential for Advanced Workflows)

Many effective workflows leverage MCP servers for research and verification:

- **Brave Search** - For researching best practices and current information
- **Puppeteer** - For extracting content from documentation sources
- **Context7** - For framework-specific guidance

See the [official MCP setup guide](https://docs.cline.bot/mcp/configuring-mcp-servers) for configuration instructions.

## Understanding Workflows

Before setting up workflows, read [Rules vs Workflows](../integration/rules-vs-workflows.md) to understand:

- How workflows differ from rules
- When to use global vs project-specific workflows
- How workflows are invoked and executed

## Setting Up Global Workflows

Global workflows apply across all your projects and contain reusable automation processes.

### 1. Create the Global Workflows Directory

```bash
mkdir -p ~/Documents/Cline/.clinerules/workflows
```
### 2. Create Your First Global Workflow

**~/Documents/Cline/.clinerules/workflows/code-review.md**

## Code Review Workflow

This workflow guides you through performing a comprehensive code review.

## Steps

1. **Analyze Changes**
   - Review the diff for the current branch
   - Identify modified files and their purposes
   - Check for potential breaking changes

2. **Code Quality Check**
   - Verify coding standards compliance
   - Check for proper error handling
   - Ensure adequate test coverage

3. **Security Review**
   - Look for potential security vulnerabilities
   - Verify input validation
   - Check for sensitive data exposure

4. **Documentation Review**
   - Ensure code is properly documented
   - Verify README updates if needed
   - Check for API documentation updates

5. **Final Recommendations**
   - Provide specific feedback
   - Suggest improvements
   - Approve or request changes

### 3. Create Additional Global Workflows

**~/Documents/Cline/.clinerules/workflows/project-setup.md**

## Project Setup Workflow

This workflow helps you set up a new project with proper structure and configuration.

## Steps

1. **Initialize Project Structure**
   - Create appropriate directory structure
   - Set up version control
   - Create initial configuration files

2. **Configure Development Environment**
   - Set up package management
   - Configure build tools
   - Set up testing framework

3. **Create Documentation**
   - Initialize README with project overview
   - Set up API documentation structure
   - Create contribution guidelines

4. **Set Up Quality Assurance**
   - Configure linting and formatting
   - Set up pre-commit hooks
   - Initialize testing structure

5. **Final Setup**
   - Create initial commit
   - Set up CI/CD pipeline basics
   - Document setup process

## MCP-Powered Workflows

Advanced workflows can leverage MCP servers for research-driven development:

```bash
~/Documents/Cline/.clinerules/workflows/research-and-document.md
```

## Research and Document Workflow

This workflow uses MCP servers to research and create accurate documentation.

## Steps

1. **Research Phase**
   - Use Brave Search to find current best practices
   - Extract content from official documentation with Puppeteer
   - Cross-reference multiple authoritative sources

2. **Verification Phase**
   - Fact-check technical claims against official sources
   - Verify code examples work with current versions
   - Validate installation and setup instructions

3. **Documentation Phase**
   - Create comprehensive documentation
   - Include verified examples and procedures
   - Add source citations and last-updated dates

4. **Quality Assurance**
   - Review for accuracy and completeness
   - Test all provided examples
   - Schedule regular re-verification

```bash
~/Documents/Cline/.clinerules/workflows/verify-tech-stack.md
```

## Tech Stack Verification Workflow

This workflow verifies and updates technology stack information.

## Steps

1. **Current State Analysis**
   - Review existing tech stack documentation
   - Identify frameworks and libraries in use
   - Note version numbers and dependencies

2. **Research Latest Versions**
   - Use Brave Search to find current stable versions
   - Check official documentation for breaking changes
   - Research security updates and recommendations

3. **Compatibility Check**
   - Verify framework compatibility matrices
   - Check for deprecated features
   - Identify migration requirements

4. **Update Documentation**
   - Update version numbers and compatibility info
   - Add migration notes if needed
   - Document verification date and sources
```bash
~/Documents/Cline/.clinerules/workflows/update-rules-workflows.md
```

## Update Rules & Workflows

This workflow guides you through updating your project's .clinerules/ files to ensure they remain aligned with your project's current state and needs.

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

## Setting Up Project-Specific Workflows

Project workflows are specific to individual projects and handle project-unique processes.

### 1. Create Project Workflows Directory

For each project, create:

```bash
mkdir .clinerules/workflows
```
### 2. Create Project-Specific Workflows

```bash
your-project/.clinerules/workflows/deploy-staging.md
```

## Deploy to Staging Workflow

This workflow handles deployment to the staging environment.

## Prerequisites
- All tests passing
- Code reviewed and approved
- Staging environment available

## Steps

1. **Pre-deployment Checks**
   - Verify test suite passes
   - Check for breaking changes
   - Validate environment variables

2. **Build Process**
   - Run production build
   - Optimize assets
   - Generate deployment artifacts

3. **Deploy**
   - Deploy to staging server
   - Run database migrations if needed
   - Update configuration

4. **Post-deployment Verification**
   - Run smoke tests
   - Verify key functionality
   - Check logs for errors

5. **Notification**
   - Notify team of deployment
   - Update deployment tracking
   - Document any issues

## Using Workflows

### Invoking Workflows

Workflows are invoked using slash commands in Cline:

```text
/code-review.md          # Global workflow
/deploy-staging.md       # Project workflow
```
### Workflow Best Practices

1. **Keep workflows focused** - Each workflow should handle one specific process
2. **Make steps actionable** - Each step should be clear and executable
3. **Include prerequisites** - List what needs to be ready before starting
4. **Add verification steps** - Include checks to ensure each step completed successfully
5. **Document outcomes** - Specify what should happen after workflow completion

## Testing Your Workflows

### Verify Global Workflows

1. Open any project in VSCode
2. Start a new Cline conversation
3. Type `/workflow-name.md` to test invocation
4. Verify Cline follows the workflow steps

### Verify Project Workflows

1. Open a project with `.clinerules/workflows/` directory
2. Start a new conversation
3. Type `/project-workflow.md` to test
4. Ensure project-specific context is used

## Troubleshooting

### Workflows Not Found

- Check file location: `~/Documents/Cline/.clinerules/workflows/` for global workflows
- Verify project workflows are in `.clinerules/workflows/` at project root
- Ensure files have `.md` extension
- Use exact filename when invoking: `/workflow-name.md`

### Workflows Not Executing Properly

- Verify workflow steps are clear and actionable
- Check that prerequisites are documented
- Ensure workflow doesn't conflict with project rules
- Restart VSCode if needed

### Permission Issues

- Ensure Cline can read workflow files
- Check file permissions on workflow directories
- Verify VSCode has access to the directories

## Advanced Workflow Patterns

### Conditional Workflows

Create workflows that adapt based on project context:

## Conditional Deploy Workflow

## Steps

1. **Determine Environment**
   - If branch is 'main': deploy to production
   - If branch is 'develop': deploy to staging
   - Otherwise: deploy to development

2. **Environment-Specific Steps**
   - Production: require manual approval
   - Staging: run full test suite
   - Development: quick deployment

### Workflow Chaining

Create workflows that can call other workflows:

## Full Release Workflow

## Steps

1. **Pre-release**
   - Run `/code-review.md` workflow
   - Run `/test-suite.md` workflow

2. **Release**
   - Run `/deploy-production.md` workflow
   - Run `/post-deploy-verification.md` workflow

## Workflow Evolution

### Track What Works

- Note which workflows are used frequently
- Identify workflows that need refinement
- Observe which steps are often skipped or modified

### Refine Over Time

- Update workflows based on experience
- Add new workflows for emerging patterns
- Remove or consolidate redundant workflows
- Keep workflows current with project changes

## Integration with Rules

Workflows work best when combined with rules:

- **Rules provide context** - Help workflows understand project standards
- **Workflows provide process** - Give step-by-step guidance for complex tasks
- **Together they create consistency** - Rules ensure quality, workflows ensure process

## Next Steps

1. **Start simple** - Create one or two basic workflows
2. **Test thoroughly** - Verify workflows work as expected
3. **Iterate based on usage** - Refine workflows based on real usage
4. **Share successful patterns** - Document what works for your team

Remember: The best workflow system is one you actually use and maintain. Start with your most common processes and build from there.
