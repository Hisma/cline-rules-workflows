# Project Update Workflow

This workflow guides you through updating an existing project to ensure it stays current with latest frameworks, security updates, and best practices.

## Prerequisites

- **Context7 MCP server configured** (see [MCP Server Requirements](../rules/mcp-server-requirements.md)) - *Only needed for projects using frameworks/libraries*
- **Brave Search MCP server configured** - *Only needed if researching framework alternatives*
- **Puppeteer MCP server configured** - *Only needed for additional research*
- Existing project with established tech stack
- Understanding of project's current state and requirements
- Backup or version control of current project state

## When to Use This Workflow

### Regular Maintenance (Monthly/Quarterly)

- Dependency updates and security patches
- Framework version updates
- Documentation updates
- Performance optimizations

### Major Updates

- Framework major version upgrades
- Architecture changes
- New feature implementations
- Technology stack changes

### Security Updates

- Critical security vulnerabilities
- Dependency security patches
- Authentication/authorization updates
- Data protection compliance

## Workflow Steps

### 1. Project Assessment

**Document Current State:**


## Project Update Assessment - [Date]

### Current Tech Stack
- Frontend: [Framework and version]
- Backend: [Framework and version]
- Database: [Type and version]
- Key Dependencies: [List major dependencies]

### Known Issues
- [List any known bugs or technical debt]
- [Performance issues]
- [Security concerns]

### Update Goals
- [What you want to achieve with this update]
- [Priority level: Critical/High/Medium/Low]
```
### 2. Framework Documentation (if applicable)

**For projects using frameworks/libraries (React, Vue, Express, etc.):**

```xml
<use_mcp_tool>
<server_name>github.com/upstash/context7-mcp</server_name>
<tool_name>resolve-library-id</tool_name>
<arguments>
{
  "libraryName": "[Your main framework, e.g., 'React']"
}
</arguments>
</use_mcp_tool>
```
**Get latest documentation and migration guides:**

```xml
<use_mcp_tool>
<server_name>github.com/upstash/context7-mcp</server_name>
<tool_name>get-library-docs</tool_name>
<arguments>
{
  "context7CompatibleLibraryID": "[library ID from previous step]",
  "topic": "migration guide breaking changes updates",
  "tokens": 10000
}
</arguments>
</use_mcp_tool>
```
**For simple projects (basic HTML/CSS, documentation sites, static sites):**

- Skip Context7 if not using complex frameworks
- Focus on dependency updates and security patches
- Use standard package manager update commands (`npm update`, `yarn upgrade`, etc.)

### 3. Additional Research (only if needed)

**Use Brave Search + Puppeteer only when:**

- Context7 doesn't support your specific framework
- Considering switching to a different framework entirely
- Need community insights on complex migration strategies
- Context7 information seems incomplete for your use case

```xml
<use_mcp_tool>
<server_name>brave-search</server_name>
<tool_name>brave_web_search</tool_name>
<arguments>
{
  "query": "[specific migration question not covered by Context7]",
  "count": 5
}
</arguments>
</use_mcp_tool>
```
### 4. Create Update Plan

**Document your update strategy:**


## Update Plan - [Date]

### Phase 1: Preparation
- [ ] Backup current project state
- [ ] Create feature branch for updates
- [ ] Document current functionality
- [ ] Set up testing environment

### Phase 2: Dependencies
- [ ] Update package.json/requirements.txt
- [ ] Resolve dependency conflicts
- [ ] Update lock files
- [ ] Test basic functionality

### Phase 3: Framework Updates
- [ ] Update main framework
- [ ] Address breaking changes
- [ ] Update code patterns
- [ ] Update configuration files

### Phase 4: Testing and Validation
- [ ] Run existing tests
- [ ] Manual testing of key features
- [ ] Performance testing
- [ ] Security validation

### Phase 5: Documentation
- [ ] Update README and docs
- [ ] Update tech stack documentation
- [ ] Document changes made
- [ ] Update deployment instructions

### Breaking Changes to Address:
- [List specific breaking changes found]
- [Migration steps for each]
- [Testing requirements for each]

### Rollback Plan:
- [How to revert if updates fail]
- [Backup restoration process]
- [Communication plan for rollback]
```
### 5. Execute Updates

**Follow your plan systematically:**

1. **Create Update Branch**

   ```bash
   git checkout -b update/[framework]-[version]-[date]
   ```
2. **Update Dependencies Gradually**
   - Start with patch updates
   - Then minor updates
   - Finally major updates
   - Test after each group

3. **Address Breaking Changes**
   - Follow official migration guides from Context7
   - Update code patterns one at a time
   - Test each change before proceeding

4. **Update Configuration**
   - Build tools configuration
   - Environment variables
   - Deployment scripts
   - CI/CD pipelines

### 6. Testing and Validation

**Comprehensive testing approach:**


## Testing Checklist

### Automated Tests
- [ ] Unit tests pass
- [ ] Integration tests pass
- [ ] End-to-end tests pass
- [ ] Performance tests within acceptable range

### Manual Testing
- [ ] Core user flows work correctly
- [ ] Authentication/authorization functions
- [ ] Data persistence works
- [ ] UI/UX remains consistent
- [ ] Mobile responsiveness maintained

### Security Testing
- [ ] No new security vulnerabilities
- [ ] Authentication still secure
- [ ] Data validation working
- [ ] HTTPS and security headers correct

### Performance Testing
- [ ] Load times acceptable
- [ ] Memory usage reasonable
- [ ] Database queries optimized
- [ ] Bundle sizes reasonable
```
### 7. Documentation Updates

**Update all relevant documentation:**

1. **Tech Stack Documentation**
   - Update version numbers
   - Note breaking changes addressed
   - Update installation instructions
   - Add new best practices

2. **Project Documentation**
   - Update README
   - Update API documentation
   - Update deployment guides
   - Update troubleshooting guides

3. **Change Documentation**

   
   ## Update Log - [Date]
   
   ### Updated Components
   - [Framework]: [old version] → [new version]
   - [Library]: [old version] → [new version]
   
   ### Breaking Changes Addressed
   - [Change 1]: [How it was addressed]
   - [Change 2]: [How it was addressed]
   
   ### New Features Available
   - [Feature 1]: [Description and usage]
   - [Feature 2]: [Description and usage]
   
   ### Deprecated Features Removed
   - [Feature 1]: [Replacement or alternative]
   - [Feature 2]: [Replacement or alternative]
   ```
### 8. Deployment and Monitoring

**Careful deployment process:**

1. **Staging Deployment**
   - Deploy to staging environment
   - Run full test suite
   - Performance monitoring
   - User acceptance testing

2. **Production Deployment**
   - Deploy during low-traffic period
   - Monitor error rates
   - Monitor performance metrics
   - Have rollback plan ready

3. **Post-Deployment Monitoring**
   - Monitor for 24-48 hours
   - Check error logs
   - Monitor user feedback
   - Performance metrics tracking

## Technology-Specific Considerations

### Frontend Framework Updates

- **Component API Changes**: Update component usage patterns
- **State Management**: Update state management patterns
- **Routing**: Update routing configuration
- **Build Tools**: Update build configuration

### Backend Framework Updates

- **API Changes**: Update endpoint implementations
- **Middleware**: Update middleware configuration
- **Database**: Update ORM/database patterns
- **Authentication**: Update auth patterns

### Database Updates

- **Schema Changes**: Plan and execute migrations
- **Query Updates**: Update query patterns
- **Performance**: Monitor query performance
- **Backup**: Ensure backup compatibility

### Simple Projects (No Frameworks)

- **Dependency Updates**: Update npm/yarn packages
- **Security Patches**: Apply security updates
- **Documentation**: Update README and docs
- **Testing**: Ensure functionality still works

## Best Practices

### Update Frequency

- **Security Updates**: Immediate (within 24-48 hours)
- **Patch Updates**: Weekly or bi-weekly
- **Minor Updates**: Monthly
- **Major Updates**: Quarterly or as needed

### Risk Management

- Always backup before updates
- Test in staging environment first
- Have rollback plan ready
- Monitor closely after deployment
- Update during low-traffic periods

### Communication

- Notify team of planned updates
- Document all changes made
- Share update results with team
- Update project documentation

### Automation

- Use dependency update tools (Dependabot, Renovate)
- Automate testing pipelines
- Automate deployment processes
- Monitor for security vulnerabilities

## Troubleshooting

### Update Failures

- **Dependency Conflicts**: Use resolution strategies in package manager
- **Breaking Changes**: Follow official migration guides carefully
- **Test Failures**: Address failing tests before proceeding
- **Build Failures**: Check build tool configuration

### Performance Issues

- **Bundle Size**: Analyze and optimize bundle size
- **Runtime Performance**: Profile and optimize bottlenecks
- **Memory Leaks**: Check for memory leaks in updated code
- **Database Performance**: Optimize queries if needed

### Rollback Scenarios

- **Critical Bugs**: Immediate rollback to previous version
- **Performance Degradation**: Rollback and investigate
- **User Experience Issues**: Rollback and plan fixes
- **Security Issues**: Immediate rollback and security review

## Success Criteria

Project update is successful when:

- [ ] All tests pass
- [ ] Performance metrics maintained or improved
- [ ] No new security vulnerabilities
- [ ] User experience maintained or improved
- [ ] Documentation updated
- [ ] Team trained on changes
- [ ] Monitoring shows stable operation
- [ ] Rollback plan tested and ready

## Integration with Other Workflows

### Before Updates

- Run [Verify Tech Stack Workflow](verify-tech-stack.md) to identify what needs updating
- Use [Research and Document Workflow](research-and-document.md) only if considering framework changes

### During Updates

- Follow [Code Review Process](code-review-process.md) for all changes
- Use [Project Setup Workflow](project-setup.md) if major architecture changes

### After Updates

- Run [Project Cleanup Workflow](project-cleanup.md) to clean up old code
- Update project templates with lessons learned

## MCP Tool Usage Summary

### Context7 (Primary for Framework Projects)

- **When**: Projects using React, Vue, Express, Django, etc.
- **Purpose**: Get latest official documentation and migration guides
- **Benefit**: Always current, authoritative information

### Brave Search (Secondary/Research)

- **When**: Context7 doesn't support your framework OR considering framework changes
- **Purpose**: Research alternatives, community insights
- **Benefit**: Broader perspective, community knowledge

### Puppeteer (Rare/Specific Cases)

- **When**: Need to extract specific content not available through other tools
- **Purpose**: Deep content extraction from official sites
- **Benefit**: Access to dynamic content

This workflow ensures your projects stay current, secure, and performant while minimizing risks and maintaining stability.
