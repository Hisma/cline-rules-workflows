# Research and Document Workflow

This workflow guides you through researching a technical topic and creating accurate, well-sourced documentation using MCP tools.

## Prerequisites

- Brave Search MCP server configured (see [MCP Server Requirements](../global/rules/mcp-server-requirements.md))
- Puppeteer MCP server configured (for content extraction)
- Context7 MCP server configured (only needed if researching specific frameworks)
- Topic or question to research
- Understanding of your documentation project's standards (see rules files)

## Workflow Steps

### 1. Initial Research Phase

**Start with broad context search using Brave Search:**

```xml
<use_mcp_tool>
<server_name>brave-search</server_name>
<tool_name>brave_web_search</tool_name>
<arguments>
{
  "query": "[your topic] overview documentation",
  "count": 10
}
</arguments>
</use_mcp_tool>
```
**Analyze the search results and identify:**

- Official documentation sources
- Authoritative technical sources
- Recent updates or changes
- Community discussions and issues

### 2. Deep Dive Research

**For each promising source, use Puppeteer to extract detailed content:**

```xml
<use_mcp_tool>
<server_name>puppeteer</server_name>
<tool_name>puppeteer_navigate</tool_name>
<arguments>
{
  "url": "[official documentation URL]"
}
</arguments>
</use_mcp_tool>
```
**Extract the full page content:**

```xml
<use_mcp_tool>
<server_name>puppeteer</server_name>
<tool_name>puppeteer_evaluate</tool_name>
<arguments>
{
  "script": "document.body.innerText"
}
</arguments>
</use_mcp_tool>
```
**For specific sections, use targeted extraction:**

```xml
<use_mcp_tool>
<server_name>puppeteer</server_name>
<tool_name>puppeteer_evaluate</tool_name>
<arguments>
{
  "script": "document.querySelector('.documentation-content').innerText"
}
</arguments>
</use_mcp_tool>
```
### 3. Framework Documentation (if applicable)

**If researching specific frameworks or libraries, use Context7 for official documentation:**

```xml
<use_mcp_tool>
<server_name>Context7</server_name>
<tool_name>resolve-library-id</tool_name>
<arguments>
{
  "libraryName": "[framework name]"
}
</arguments>
</use_mcp_tool>
```
**Then get the latest documentation:**

```xml
<use_mcp_tool>
<server_name>Context7</server_name>
<tool_name>get-library-docs</tool_name>
<arguments>
{
  "context7CompatibleLibraryID": "[library ID from previous step]",
  "topic": "[specific topic you're researching]"
}
</arguments>
</use_mcp_tool>
```
**Note**: Context7 is most useful for complex frameworks. For simple documentation projects using basic HTML/CSS/Markdown, you may not need Context7.

### 4. Cross-Verification

**Search for additional sources to verify information:**

```xml
<use_mcp_tool>
<server_name>brave-search</server_name>
<tool_name>brave_web_search</tool_name>
<arguments>
{
  "query": "[specific technical detail] official specification",
  "count": 5
}
</arguments>
</use_mcp_tool>
```
**Check for recent changes or updates:**

```xml
<use_mcp_tool>
<server_name>brave-search</server_name>
<tool_name>brave_web_search</tool_name>
<arguments>
{
  "query": "[topic] changes updates 2024 2025",
  "count": 5
}
</arguments>
</use_mcp_tool>
```
### 5. Structure Documentation

**Create a new documentation file following your project's standards:**

```markdown
# [Topic Title]

## Overview
[Brief description of what this covers]

## Key Concepts
[Main concepts and terminology]

## Implementation Details
[Step-by-step instructions or explanations]

### Example
[Working code examples or demonstrations]

## Common Issues
[Known problems and solutions]

## References
- [Source 1 - Official Documentation](URL)
- [Source 2 - Specification](URL)
- [Source 3 - Community Resource](URL)

## Last Verified
[Date when information was last checked]
```
### 6. Fact-Checking Process

**For each major claim or instruction:**

1. **Identify the source** - Where did this information come from?
2. **Verify currency** - Is this information still current?
3. **Test if possible** - Can the instructions be followed successfully?
4. **Cross-reference** - Do multiple sources agree?

**Document your verification process:**

```markdown
## Verification Notes
- **Claim**: [Specific technical claim]
- **Source**: [Primary source URL]
- **Verified**: [Date]
- **Method**: [How you verified - testing, cross-reference, etc.]
- **Status**: [Current/Outdated/Needs Review]
```
### 7. Quality Review

**Before finalizing, check against project standards:**

- [ ] All technical claims have sources
- [ ] Instructions are clear and actionable
- [ ] Examples work as written
- [ ] Links are current and accessible
- [ ] Content is organized logically
- [ ] Language is appropriate for target audience
- [ ] Follows project style guidelines (see tech stack rules)
- [ ] Meets project quality standards (see current requirements)

### 8. Documentation Maintenance

**Set up for future updates:**

```markdown
## Maintenance Schedule
- **Next Review**: [Date 3 months from creation]
- **Update Triggers**: 
  - New version releases
  - Community reports of issues
  - Changes in official documentation
- **Review Process**: Re-run this research workflow
```
## Advanced Techniques

### Extracting Structured Data

**For API documentation or structured content:**

```xml
<use_mcp_tool>
<server_name>puppeteer</server_name>
<tool_name>puppeteer_evaluate</tool_name>
<arguments>
{
  "script": "Array.from(document.querySelectorAll('h2')).map(h => ({title: h.textContent, content: h.nextElementSibling?.textContent}))"
}
</arguments>
</use_mcp_tool>
```
### Monitoring for Changes

**Set up searches to monitor for updates:**

```xml
<use_mcp_tool>
<server_name>brave-search</server_name>
<tool_name>brave_web_search</tool_name>
<arguments>
{
  "query": "[topic] changelog release notes site:official-domain.com",
  "count": 5
}
</arguments>
</use_mcp_tool>
```
### Research Documentation Template

**Keep track of your research process:**

```markdown
# Research Log: [Topic]

## Research Questions
- [Question 1]
- [Question 2]

## Sources Investigated
1. **[Source Name]**
   - URL: [URL]
   - Date Accessed: [Date]
   - Key Findings: [Summary]
   - Reliability: [High/Medium/Low]

## Search Queries Used
- "[Query 1]" - [Results summary]
- "[Query 2]" - [Results summary]

## Verification Steps
- [Step 1 and result]
- [Step 2 and result]

## Conclusions
[Final conclusions based on research]

## Follow-up Needed
- [Items requiring additional research]
- [Questions that remain unanswered]
```
## Integration with Project Rules

This workflow should be used in conjunction with your project's rules:

- **Project Overview**: Ensure research aligns with project purpose and target users
- **Tech Stack**: Follow established documentation standards and MCP integration patterns
- **Current Requirements**: Address current priorities and quality focus areas

## Best Practices

1. **Always start with official sources** - Look for official documentation first
2. **Use multiple verification methods** - Don't rely on a single source
3. **Document your process** - Keep track of how you verified information
4. **Test when possible** - Try to reproduce examples and instructions
5. **Stay current** - Set up regular review cycles for important documentation
6. **Cite sources** - Always provide links to your sources
7. **Be transparent** - Note when information couldn't be verified or is uncertain

## Common Pitfalls

- **Outdated information** - Always check publication dates
- **Unofficial sources** - Prefer official documentation over blog posts
- **Incomplete testing** - Don't assume examples work without testing
- **Missing context** - Ensure you understand the full context of information
- **Over-reliance on single sources** - Cross-verify important claims

## Template Customization Notes

- Adapt MCP tool usage to your available servers
- Modify documentation structure to match your project's style
- Add project-specific verification steps
- Include domain-specific research techniques
- Update quality checklist based on your project's standards

This workflow ensures that all documentation is research-backed, accurate, and maintainable over time while following your project's specific standards and requirements.
