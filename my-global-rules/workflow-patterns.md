# Workflow Patterns

## Development Workflow

### Sequential Thinking Approach
- Break down complex problems into clear, manageable steps
- Use systematic analysis before implementing solutions
- Document thought process and decision rationale
- Allow for iteration and refinement of approach
- Track branches and alternative solutions considered

### Tool Usage Philosophy
- Use the most appropriate tool for each specific task
- Combine multiple tools when necessary for comprehensive solutions
- Always wait for confirmation of tool success before proceeding
- Document tool usage patterns for future reference
- Prefer proactive tool usage over reactive responses

### Task Management
- Never complete tasks without explicit confirmation
- Ask clarifying questions when requirements are ambiguous
- Break large tasks into smaller, verifiable steps
- Maintain clear communication throughout the process
- Provide regular progress updates

## Git Workflow

### Commit Standards
- Write clear, descriptive commit messages
- Use conventional commit format when appropriate
- Make atomic commits that represent single logical changes
- Include context about why changes were made
- Reference issues or tickets when applicable

### Branch Management
- Use feature branches for new development
- Keep branches focused and short-lived
- Use descriptive branch names that indicate purpose
- Regularly sync with main/master branch
- Clean up merged branches promptly

### Code Review Process
- Review code for logic, readability, and maintainability
- Check for security vulnerabilities and performance issues
- Verify tests are included and passing
- Ensure documentation is updated
- Provide constructive feedback with specific suggestions

## Project Setup Patterns

### Initial Setup
- Create clear project structure from the start
- Set up development environment consistently
- Configure linting and formatting tools
- Establish testing framework early
- Document setup process for team members

### Configuration Management
- Keep configuration separate from code
- Use environment variables for deployment-specific settings
- Version control configuration templates
- Document all configuration options
- Implement configuration validation

### Dependency Management
- Keep dependencies up to date
- Use lock files for reproducible builds
- Regularly audit for security vulnerabilities
- Document why specific dependencies were chosen
- Minimize dependency bloat

## Testing Strategy

### Test-Driven Development
- Write tests before implementing features when appropriate
- Use tests to clarify requirements and edge cases
- Maintain high test coverage for critical paths
- Keep tests simple and focused
- Use descriptive test names that explain scenarios

### Testing Pyramid
- Unit tests for business logic and algorithms
- Integration tests for component interactions
- End-to-end tests for critical user workflows
- Performance tests for bottlenecks
- Security tests for vulnerable areas

### Continuous Integration
- Run tests automatically on every commit
- Fail builds on test failures or linting errors
- Use consistent testing environments
- Monitor test execution time and flakiness
- Maintain fast feedback loops

## Documentation Workflow

### Living Documentation
- Keep documentation close to the code
- Update documentation with code changes
- Use examples and code snippets liberally
- Focus on the "why" not just the "what"
- Regular review and cleanup of outdated content

### README Standards
- Clear project description and purpose
- Step-by-step setup instructions
- Usage examples and common scenarios
- Troubleshooting guide for common issues
- Contributing guidelines for team projects

### API Documentation
- Document all public interfaces
- Include request/response examples
- Specify error conditions and codes
- Provide SDK or client library examples
- Keep documentation in sync with implementation

## Deployment Patterns

### Environment Management
- Use consistent environments (dev, staging, prod)
- Automate deployment processes
- Implement proper rollback procedures
- Monitor deployments for issues
- Use feature flags for gradual rollouts

### Release Management
- Use semantic versioning for releases
- Maintain changelog with user-facing changes
- Test releases in staging environment first
- Coordinate releases with stakeholders
- Plan for rollback scenarios

### Monitoring and Observability
- Implement comprehensive logging
- Set up alerting for critical issues
- Monitor key performance metrics
- Use distributed tracing for complex systems
- Regular review of monitoring effectiveness

## Communication Patterns

### Progress Updates
- Provide regular status updates on long-running tasks
- Communicate blockers and dependencies early
- Share learnings and discoveries with the team
- Document decisions and their rationale
- Ask for help when stuck

### Knowledge Sharing
- Conduct regular code reviews
- Share interesting findings in team meetings
- Write post-mortems for significant issues
- Mentor junior team members
- Contribute to team knowledge base

### Stakeholder Communication
- Translate technical concepts for non-technical audiences
- Provide realistic timelines with buffer for unknowns
- Communicate risks and trade-offs clearly
- Regular check-ins on project progress
- Document requirements and changes

## Quality Assurance

### Code Quality Gates
- Automated linting and formatting checks
- Code coverage thresholds
- Security vulnerability scanning
- Performance regression testing
- Accessibility compliance checking

### Review Process
- Peer review for all code changes
- Architecture review for significant changes
- Security review for sensitive components
- Performance review for critical paths
- Documentation review for public APIs

### Continuous Improvement
- Regular retrospectives on process effectiveness
- Metrics tracking for key quality indicators
- Experimentation with new tools and practices
- Learning from failures and near-misses
- Sharing best practices across teams

This workflow should be adapted based on team size, project requirements, and organizational constraints.
