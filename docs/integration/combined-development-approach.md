# Combined Cline Rules & Workflows Approach

This document explains a comprehensive approach to using both Cline rules and workflows together, how to organize them effectively, and the philosophy behind an integrated setup.

## My Philosophy

### Consistency First

I believe in establishing consistent patterns across all projects. My global rules ensure that whether I'm working on a web app, mobile project, or data science experiment, certain standards remain constant.

### Context Matters

While consistency is important, each project has unique requirements. Project-specific rules and workflows allow adaptation to different technologies, team preferences, and project phases without abandoning core principles.

### Process Automation

Workflows complement rules by automating repetitive tasks and complex processes. While rules provide guidance, workflows provide executable action sequences that ensure consistency in execution.

### Research-Driven Development

MCP (Model Context Protocol) servers enable research-driven development by providing access to current information, official documentation, and fact-checking capabilities. This ensures decisions are based on accurate, up-to-date information.

### Evolution Over Perfection

Both rules and workflows have evolved significantly over time. Starting with basic guidelines and simple processes, they've been gradually refined based on what actually helps in real development scenarios.

## How I Organize My Rules

### Global Rules Structure

I keep my global rules focused on universal principles:

**coding-standards.md** - Language-agnostic best practices

- Clean code principles
- Naming conventions
- Code organization patterns
- Comment guidelines

**documentation-requirements.md** - How I document everything

- README standards
- Code documentation
- API documentation
- Change logs

**collaboration-patterns.md** - Team collaboration standards

- Communication guidelines
- Code review practices
- Knowledge sharing approaches
- Team workflow patterns

**mcp-server-requirements.md** - Essential MCP server setup

- Required MCP servers for research-driven development
- Configuration guidelines
- Usage patterns and best practices
- Integration with workflows

### Project Rules Structure

**Web Application Projects:**

1. **01-project-overview.md** - What this project does and why
2. **02-tech-stack.md** - Specific technologies and their usage
3. **03-architecture.md** - How the project is structured
4. **04-current-requirements.md** - Current development focus and priorities

**Documentation Application Projects:**

1. **01-project-overview.md** - What this project does and why
2. **02-tech-stack.md** - Specific technologies and their usage
3. **03-architecture.md** - How the project is structured
4. **04-current-requirements.md** - Current development focus and priorities

## How I Organize My Workflows

### Global Workflows Structure

I maintain global workflows for processes that apply across all projects:

**code-review-process.md** - Comprehensive code review steps

- Analyze changes and impact
- Check coding standards compliance
- Verify security considerations
- Provide actionable feedback

**project-setup.md** - New project initialization

- Create directory structure
- Set up version control
- Configure development environment
- Initialize documentation

**research-and-document.md** - MCP-powered research

- Use Brave Search for current best practices
- Extract content from official documentation
- Verify information accuracy
- Create comprehensive documentation

**verify-tech-stack.md** - Technology verification

- Research latest versions and compatibility
- Check for security updates
- Validate framework combinations
- Update documentation with findings

**project-cleanup.md** - Project maintenance and cleanup

- Remove unused dependencies
- Clean up deprecated code
- Update documentation
- Archive or remove obsolete files

**project-update.md** - Regular project maintenance

- Update dependencies to latest stable versions
- Review and update documentation
- Check for security vulnerabilities
- Optimize project structure

### Project Workflows Structure

**Web Application Projects:**

- **deploy-to-staging.md** - Project-specific deployment to staging environment
- **project-cleanup.md** - Web app specific cleanup and maintenance

**Documentation Site Projects:**

- **research-and-document.md** - Content research and documentation workflows
- **project-cleanup.md** - Documentation site cleanup and maintenance

## How I Use Rules and Workflows in Practice

### Daily Development

- **Rules**: Cline automatically references global and project rules for consistent coding practices
- **Workflows**: I invoke specific workflows for repetitive tasks like `/code-review-process.md` or `/deploy-staging.md`
- **MCP Integration**: Research workflows help verify information and stay current with best practices
- **Updates**: I update current-focus rules weekly and refine workflows based on usage

### Code Reviews

- **Rules**: Help Cline suggest improvements that align with my standards
- **Workflows**: `/code-review-process.md` provides consistent review steps
- **MCP Research**: Verify coding standards and security practices against current recommendations
- **Consistency**: Patterns make reviews faster and more focused

### Onboarding New Projects

- **Global Rules**: Provide immediate consistency across all projects
- **Setup Workflow**: `/project-setup.md` ensures consistent project initialization
- **Research Integration**: Use MCP servers to verify current best practices for the tech stack
- **Template Application**: Quickly customize project-specific rules and workflows

### Technology Research and Documentation

- **Research Workflows**: `/research-and-document.md` and `/verify-tech-stack.md` leverage MCP servers
- **Fact Checking**: Use Brave Search and Puppeteer to verify technical claims
- **Current Information**: Ensure documentation reflects latest versions and practices
- **Source Citation**: Maintain links to authoritative sources for future verification

### Project Maintenance

- **Regular Updates**: `/project-update.md` for systematic dependency and documentation updates
- **Cleanup Operations**: `/project-cleanup.md` for removing unused code and optimizing structure
- **Health Checks**: Regular workflow execution to maintain project quality
- **Documentation Sync**: Keeping project documentation current with code changes

### Deployment and Release Management

- **Staging Deployments**: `/deploy-to-staging.md` for web applications
- **Production Releases**: Following established deployment patterns
- **Quality Gates**: Ensuring all workflows pass before releases
- **Rollback Procedures**: Having tested rollback workflows ready

## MCP Integration Strategy

### Essential MCP Servers

**Brave Search** - Primary research tool

- Find current best practices and documentation
- Research framework compatibility and versions
- Verify security recommendations
- Cross-reference multiple sources

**Puppeteer** - Content extraction and verification

- Extract content from official documentation
- Verify installation instructions
- Test web-based examples
- Capture screenshots for documentation

**Context7** - Framework-specific guidance (when required)

- Get up-to-date framework documentation
- Access specific version information
- Find framework-specific best practices

### Research-Driven Workflow Examples

**Technology Research Process:**

1. Use Brave Search to find official documentation
2. Extract key information with Puppeteer
3. Cross-reference multiple authoritative sources
4. Verify examples and procedures
5. Document findings with source citations

**Documentation Verification Process:**

1. Identify claims that need verification
2. Research current information with MCP servers
3. Test procedures and examples
4. Update documentation with verified information
5. Schedule regular re-verification

## My Rule Writing Process

### For Global Rules

1. **Identify patterns** - What do I do consistently across all projects?
2. **Make it actionable** - Turn preferences into specific guidelines
3. **Test with Cline** - See how Cline interprets and applies the rules
4. **Refine based on results** - Adjust wording for better AI understanding

### For Project Rules

1. **Start with template** - Use my project templates as a starting point
2. **Customize for context** - Adapt to specific technologies and requirements
3. **Update regularly** - Reflect current priorities and learnings
4. **Keep it current** - Remove outdated information promptly

## Tips for Effective Rules

### What Works Well

- **Bullet points** over paragraphs
- **Specific examples** over abstract concepts
- **Current context** over historical information
- **Actionable guidelines** over philosophical statements

### What Doesn't Work

- **Too much detail** - Cline gets overwhelmed
- **Contradictory rules** - Creates confusion
- **Outdated information** - Leads to poor suggestions
- **Personal preferences without context** - Hard for AI to apply appropriately

## Measuring Success

I know my rules are working when:

- Cline's suggestions align with my coding style
- Code reviews focus on logic rather than style issues
- New project setup is faster and more consistent
- I spend less time explaining context to Cline

## Future Improvements

### Short Term

- Add more specific examples to existing rules
- Create templates for new project types I'm exploring
- Better integration between global and project rules

### Long Term

- Experiment with rule automation based on project analysis
- Develop team-specific rule templates
- Create rule effectiveness metrics
