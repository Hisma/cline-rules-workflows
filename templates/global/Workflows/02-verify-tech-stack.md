# Verify Tech Stack with Context7 Workflow

This workflow ensures you're using the latest framework and API documentation when setting up or updating your project's tech stack.

## Prerequisites

- **Context7 MCP server configured** (see [MCP Server Requirements](../rules/mcp-server-requirements.md)) - *Only needed for projects using frameworks/libraries*
- **Brave Search MCP server configured** - *Only needed for researching framework alternatives*
- **Puppeteer MCP server configured** - *Only needed for additional research*
- List of frameworks, libraries, and APIs your project uses
- Understanding of your project's requirements

## Workflow Steps

### 1. Identify Technologies to Verify

**Create a list of all technologies that need verification:**

- Frontend frameworks (React, Vue, Angular, etc.)
- Backend frameworks (Express, FastAPI, Spring Boot, etc.)
- Databases and ORMs (PostgreSQL, MongoDB, Prisma, etc.)
- Testing frameworks (Jest, Cypress, Playwright, etc.)
- Build tools (Vite, Webpack, etc.)
- Deployment platforms (Vercel, AWS, etc.)
- Third-party APIs and services

### 2. Use Context7 to Get Latest Documentation

**For each technology, resolve the library ID first:**

```xml
<use_mcp_tool>
<server_name>github.com/upstash/context7-mcp</server_name>
<tool_name>resolve-library-id</tool_name>
<arguments>
{
  "libraryName": "[framework name, e.g., 'React']"
}
</arguments>
</use_mcp_tool>
```

**Then get the latest documentation:**

```xml
<use_mcp_tool>
<server_name>github.com/upstash/context7-mcp</server_name>
<tool_name>get-library-docs</tool_name>
<arguments>
{
  "context7CompatibleLibraryID": "[library ID from previous step]",
  "topic": "[specific topic like 'getting started', 'hooks', 'routing']",
  "tokens": 10000
}
</arguments>
</use_mcp_tool>
```

### 3. Document Current Information

**For each technology, record:**

## [Technology Name] Verification

**Library ID**: [Context7 library ID]
**Latest Version**: [Current stable version]
**Last Verified**: [Date]
**Key Changes**: [Any breaking changes or new features]
**Documentation URL**: [Official documentation link]

### Current Best Practices

- [Practice 1 from latest docs]
- [Practice 2 from latest docs]
- [Practice 3 from latest docs]

### Installation/Setup

```bash
[Latest installation commands]
```

### Basic Usage Example

```javascript
[Current syntax example from latest docs]
```

### 4. Additional Research (only if needed)

**Use Brave Search + Puppeteer only when:**

- Context7 doesn't support your specific framework
- You need community insights beyond official documentation
- Context7 information seems incomplete
- You're considering switching frameworks

```xml
<use_mcp_tool>
<server_name>brave-search</server_name>
<tool_name>brave_web_search</tool_name>
<arguments>
{
  "query": "[specific question not covered by Context7]",
  "count": 5
}
</arguments>
</use_mcp_tool>
```

### 5. Compare with Current Project Setup

**Check your current project against latest information:**

- Are you using the latest stable version?
- Are there any deprecated patterns in your code?
- Are there new features that could benefit your project?
- Do your dependencies need updating?

### 6. Update Tech Stack Documentation

**Update your project's tech stack rules with verified information:**

- Current version numbers
- Latest syntax and patterns
- Updated installation instructions
- New best practices
- Deprecated feature warnings

### 7. Create Update Plan

**If updates are needed, plan the migration:**

- Identify breaking changes
- Plan migration steps
- Test in development environment
- Update documentation and examples

## Example: Verifying React

### Step 1: Resolve React Library ID

```xml
<use_mcp_tool>
<server_name>github.com/upstash/context7-mcp</server_name>
<tool_name>resolve-library-id</tool_name>
<arguments>
{
  "libraryName": "React"
}
</arguments>
</use_mcp_tool>
```

### Step 2: Get React Documentation

```xml
<use_mcp_tool>
<server_name>github.com/upstash/context7-mcp</server_name>
<tool_name>get-library-docs</tool_name>
<arguments>
{
  "context7CompatibleLibraryID": "/facebook/react",
  "topic": "hooks and components",
  "tokens": 10000
}
</arguments>
</use_mcp_tool>
```

### Step 3: Cross-Verify with Brave Search

```xml
<use_mcp_tool>
<server_name>brave-search</server_name>
<tool_name>brave_web_search</tool_name>
<arguments>
{
  "query": "React 18 latest features 2025 official documentation",
  "count": 5
}
</arguments>
</use_mcp_tool>
```

### Step 4: Document Findings

## React Verification

**Library ID**: /facebook/react
**Latest Version**: 18.3.1
**Last Verified**: 2025-05-31
**Key Changes**: Server Components stable, new use() hook
**Documentation URL**: <https://react.dev>

### Current Best Practices

- Use function components with hooks
- Implement Server Components for better performance
- Use Suspense for data fetching
- Prefer built-in hooks over custom solutions

### Installation

```bash
npm install react@latest react-dom@latest
```

### Basic Component Example

```jsx
import { useState, useEffect } from 'react';

function MyComponent() {
  const [data, setData] = useState(null);
  
  useEffect(() => {
    // Latest async pattern
    fetchData().then(setData);
  }, []);
  
  return <div>{data ? data.title : 'Loading...'}</div>;
}
```

## Technology-Specific Verification

### Frontend Frameworks

- **Focus Areas**: Component patterns, state management, routing
- **Key Topics**: "components", "hooks", "routing", "state management"

### Backend Frameworks

- **Focus Areas**: API patterns, middleware, database integration
- **Key Topics**: "routing", "middleware", "database", "authentication"

### Databases and ORMs

- **Focus Areas**: Query patterns, migrations, performance
- **Key Topics**: "queries", "migrations", "performance", "schema"

### Testing Frameworks

- **Focus Areas**: Testing patterns, assertions, mocking
- **Key Topics**: "testing", "mocking", "assertions", "best practices"

## Best Practices

### Verification Frequency

- **New Projects**: Verify all technologies before starting
- **Existing Projects**: Monthly verification for critical dependencies
- **Major Updates**: Verify before any major version upgrades
- **Security Updates**: Immediate verification for security-related updates

### Documentation Standards

- Always include verification date
- Document breaking changes clearly
- Provide migration examples
- Link to official documentation
- Note any project-specific considerations

### Version Management

- Use exact version numbers in documentation
- Document upgrade paths for major versions
- Test updates in development environment first
- Keep rollback plans for major updates

## Integration with Other Workflows

### Project Setup

- Run this workflow before creating tech stack documentation
- Use verified information in project templates
- Include verification dates in project documentation

### Research and Documentation

- Use Context7 as primary source for framework information
- Cross-reference with Brave Search for additional context
- Verify examples and code snippets with Puppeteer

### Regular Maintenance

- Schedule monthly tech stack verification
- Include in project cleanup workflows
- Update project templates with latest information

## Troubleshooting

### MCP Server Issues

- Verify MCP servers are configured (see [MCP Server Requirements](../rules/mcp-server-requirements.md))
- Restart Cline if MCP servers aren't responding
- Check API keys and configuration

### Library Not Found in Context7

- Try alternative names or abbreviations
- Search for the organization name (e.g., "facebook/react")
- Use Brave Search to find the correct library identifier
- Check if the library has been renamed or moved

### Outdated Information

- Cross-reference with official documentation using Puppeteer
- Check GitHub releases for latest version information
- Use multiple sources to verify current best practices
- Document any discrepancies found

### Version Conflicts

- Check compatibility between different library versions
- Review breaking changes in release notes
- Plan migration strategy for incompatible updates
- Test thoroughly in development environment

## Success Criteria

Tech stack verification is complete when:

- [ ] All major technologies verified with Context7
- [ ] Current versions documented
- [ ] Best practices updated
- [ ] Breaking changes identified
- [ ] Migration plan created (if needed)
- [ ] Project documentation updated
- [ ] Team notified of any required changes

This workflow ensures your project always uses current, well-documented technology patterns and avoids deprecated or outdated approaches.
