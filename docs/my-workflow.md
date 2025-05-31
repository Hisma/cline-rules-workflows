# My Cline Rules Workflow

This document explains my personal approach to using Cline rules, how I organize them, and the philosophy behind my setup.

## My Philosophy

### Consistency First
I believe in establishing consistent patterns across all projects. My global rules ensure that whether I'm working on a web app, mobile project, or data science experiment, certain standards remain constant.

### Context Matters
While consistency is important, each project has unique requirements. My project-specific rules allow me to adapt to different technologies, team preferences, and project phases without abandoning my core principles.

### Evolution Over Perfection
My rules have evolved significantly over time. I started with basic guidelines and gradually refined them based on what actually helps in real development scenarios.

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

## How I Use Rules in Practice

### Daily Development
- Cline automatically references my global rules for consistent coding practices
- Project rules help Cline understand the current context and make appropriate suggestions
- I update current-focus rules weekly to reflect changing priorities

### Code Reviews
- My rules help Cline suggest improvements that align with my standards
- Consistent patterns make code reviews faster and more focused
- New team members can reference the rules to understand expectations

### Onboarding New Projects
- Global rules provide immediate consistency
- I can quickly set up project-specific rules based on my templates
- Rules help Cline understand the project faster than explaining everything each time

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
