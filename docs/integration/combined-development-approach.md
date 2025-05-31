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

**security-guidelines.md** - Security practices I always follow
- Input validation
- Authentication patterns
- Data protection
- Dependency management

**workflow-patterns.md** - My development workflows
- Git practices
- Testing approaches
- Code review guidelines
- Deployment patterns

### Project Rules Strategy

For each project, I typically create:

1. **01-project-overview.md** - What this project does and why
2. **02-tech-stack.md** - Specific technologies and their usage
3. **03-architecture.md** - How the project is structured
4. **04-current-focus.md** - What I'm working on right now

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

## Real Examples from My Workflow

### Starting a New Web Application

When I start a new web app, here's my typical process:

1. **Global rules provide the foundation** - Coding standards, documentation requirements, security guidelines
2. **Create project overview** - Explain the app's purpose, target users, key features
3. **Define tech stack** - React, TypeScript, Node.js, specific libraries and why I chose them
4. **Set architecture guidelines** - Component structure, state management, API patterns
5. **Current sprint focus** - What features I'm building this week

### Working on Data Science Projects

For ML/data projects, my approach differs:

1. **Global rules still apply** - Clean code, documentation, security
2. **Data-specific guidelines** - Data validation, model documentation, experiment tracking
3. **Notebook standards** - How to structure Jupyter notebooks, when to refactor to scripts
4. **Reproducibility requirements** - Environment management, seed setting, data versioning

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

**Context7** - Framework-specific guidance (when available)
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

## Evolution of My Rules

### Version 1: Basic Guidelines
Started with simple coding standards and basic documentation requirements. Rules were too generic and didn't provide enough context.

### Version 2: Project-Specific Focus
Added project-specific rules but made them too detailed. Cline sometimes got overwhelmed with information.

### Version 3: Balanced Approach (Current)
Found the right balance between global consistency and project flexibility. Rules are concise but comprehensive.

### Key Lessons Learned

1. **Less is more** - Concise, actionable rules work better than verbose explanations
2. **Context is crucial** - Project-specific rules dramatically improve Cline's helpfulness
3. **Regular updates matter** - Rules should evolve with your workflow and experience
4. **Examples help** - Including code examples in rules makes them more actionable

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

## Sharing and Collaboration

### What I Share Publicly
- General principles and approaches
- Template structures and organization patterns
- Lessons learned and best practices

### What I Keep Private
- Client-specific requirements
- Proprietary coding standards
- Sensitive security practices

## Getting Started with Your Own Workflow

If you're inspired to create your own system:

1. **Start simple** - Begin with basic global rules
2. **Observe patterns** - Notice what you do consistently
3. **Document as you go** - Don't try to create everything at once
4. **Iterate frequently** - Rules should evolve with your experience
5. **Focus on value** - Only create rules that actually help

Remember: The best rule system is the one you actually use and maintain. Start small, be consistent, and let it grow naturally with your workflow.
