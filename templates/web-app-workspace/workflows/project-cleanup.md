# Web Application Project Cleanup Workflow

This workflow helps you clean up and optimize your web application project, removing unused code, optimizing performance, and maintaining code quality.

## Prerequisites

- Understanding of your web application structure
- Access to analytics and monitoring data
- Backup or version control of current state
- Time allocated for thorough review (60-120 minutes for web apps)

## Steps

### 1. Run Global Cleanup First

- Execute the global project cleanup workflow: `/project-cleanup.md`
- Complete general file organization and cleanup tasks
- Return here for web application-specific cleanup

### 2. Frontend Code Cleanup

**Remove Unused Components and Code:**

- Identify unused React/Vue/Angular components
- Remove unused CSS classes and styles
- Clean up unused JavaScript functions and utilities
- Remove commented-out code blocks

**Optimize Bundle Size:**

- Analyze bundle size with webpack-bundle-analyzer or similar
- Remove unused dependencies from package.json
- Implement code splitting for large components
- Optimize imports (use tree shaking)

**Update Dependencies:**

- Check for outdated npm packages: `npm outdated`
- Update dependencies to latest stable versions
- Remove deprecated packages
- Audit for security vulnerabilities: `npm audit`

### 3. Backend Code Cleanup

**API Cleanup:**

- Remove unused API endpoints
- Clean up deprecated routes
- Optimize database queries
- Remove unused middleware

**Database Cleanup:**

- Remove unused database tables/collections
- Clean up old migration files
- Optimize database indexes
- Archive old data if appropriate

### 4. Asset and Media Optimization

**Image Optimization:**

- Compress images without quality loss
- Convert to modern formats (WebP, AVIF)
- Remove unused images and assets
- Implement responsive image loading

**Static Asset Cleanup:**

- Remove unused fonts
- Clean up old CSS/JS files
- Optimize SVG files
- Remove duplicate assets

### 5. Performance Optimization

**Frontend Performance:**

- Implement lazy loading for components
- Optimize CSS delivery (critical CSS)
- Minimize and compress JavaScript bundles
- Implement service worker caching

**Backend Performance:**

- Optimize API response times
- Implement caching strategies
- Optimize database queries
- Review and optimize server configurations

### 6. Code Quality Improvements

**Linting and Formatting:**

- Run ESLint and fix issues
- Apply Prettier formatting consistently
- Update linting rules if needed
- Fix TypeScript errors and warnings

**Testing Cleanup:**

- Remove obsolete tests
- Update test snapshots
- Improve test coverage for critical paths
- Clean up test utilities and mocks

### 7. Security and Compliance

**Security Audit:**

- Run security vulnerability scans
- Update packages with security issues
- Review and update authentication logic
- Check for exposed sensitive data

**Privacy and Compliance:**

- Review data collection practices
- Update privacy policy if needed
- Ensure GDPR/CCPA compliance
- Clean up unnecessary user data

## Web Application-Specific Checklist

### Frontend Cleanup

- [ ] Unused components removed
- [ ] CSS optimized and unused styles removed
- [ ] JavaScript bundle size optimized
- [ ] Dependencies updated and unused ones removed
- [ ] Images and assets optimized
- [ ] Performance metrics improved

### Backend Cleanup

- [ ] Unused API endpoints removed
- [ ] Database optimized and cleaned
- [ ] Server performance optimized
- [ ] Security vulnerabilities addressed
- [ ] Logging and monitoring optimized

### Development Environment

- [ ] Development dependencies updated
- [ ] Build process optimized
- [ ] Testing environment cleaned up
- [ ] Documentation updated
- [ ] CI/CD pipeline optimized

### Performance Metrics

- [ ] Page load times improved
- [ ] Bundle sizes reduced
- [ ] API response times optimized
- [ ] Core Web Vitals scores improved
- [ ] Lighthouse scores improved

## Common Web App Issues

### Bundle Size Problems

- **Symptoms**: Slow loading times, large JavaScript bundles
- **Solution**: Implement code splitting, remove unused dependencies, optimize imports
- **Prevention**: Regular bundle analysis, dependency audits

### Performance Regressions

- **Symptoms**: Slow page loads, poor user experience
- **Solution**: Performance profiling, optimization of critical paths
- **Prevention**: Performance monitoring, regular performance testing

### Security Vulnerabilities

- **Symptoms**: Security audit warnings, outdated dependencies
- **Solution**: Regular dependency updates, security scanning
- **Prevention**: Automated security monitoring, dependency update automation

### Code Quality Issues

- **Symptoms**: Inconsistent formatting, linting errors, test failures
- **Solution**: Automated formatting, linting fixes, test updates
- **Prevention**: Pre-commit hooks, CI/CD quality gates

## Automation Opportunities

### Automated Cleanup Scripts

```bash
# Remove unused dependencies
npx depcheck

# Find unused files
npx unimported

# Optimize images
npx imagemin-cli

# Bundle analysis
npx webpack-bundle-analyzer
```

### Performance Monitoring

- Set up automated Lighthouse CI
- Monitor Core Web Vitals
- Track bundle size changes
- Monitor API performance

### Security Automation

- Automated dependency vulnerability scanning
- Regular security audits
- Automated dependency updates (Dependabot)
- Security-focused linting rules

## Best Practices for Web App Cleanup

### Prevention Strategies

- Regular dependency updates
- Automated code quality checks
- Performance budgets and monitoring
- Regular security audits

### Execution Tips

- Test thoroughly after each cleanup step
- Use feature flags for risky changes
- Monitor performance metrics during cleanup
- Keep detailed notes of changes made

### Maintenance Planning

- Schedule monthly dependency updates
- Quarterly performance reviews
- Regular security audits
- Continuous monitoring setup

## Integration with Project Standards

This cleanup workflow should align with your project's:

- **Performance targets** (see current requirements)
- **Technical constraints** (see tech stack rules)
- **Quality standards** (see project overview)
- **Deployment processes** (see deployment workflows)

## Success Indicators

After completing this cleanup:

- Bundle sizes are optimized
- Performance metrics are improved
- Security vulnerabilities are addressed
- Code quality is enhanced
- Development experience is improved
- User experience is faster and smoother

## Performance Targets to Achieve

### Frontend Performance

- First Contentful Paint < 1.5s
- Largest Contentful Paint < 2.5s
- Cumulative Layout Shift < 0.1
- First Input Delay < 100ms

### Backend Performance

- API response times < 200ms
- Database query times optimized
- Server response times improved
- Error rates minimized

Remember: Web application cleanup is about balancing performance, maintainability, and user experience. Regular cleanup prevents technical debt and keeps your application fast and reliable.
