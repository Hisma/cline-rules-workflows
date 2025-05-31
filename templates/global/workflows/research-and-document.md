# Research and Document Workflow

This workflow guides you through researching a technical topic and creating accurate, well-sourced documentation using MCP tools.

## Prerequisites
- **Brave Search MCP server configured** (see [MCP Server Requirements](../rules/mcp-server-requirements.md)) - *Primary tool for research*
- **Puppeteer MCP server configured** - *For content extraction from official sources*
- **Context7 MCP server configured** - *Only needed after choosing specific frameworks/libraries*
- Access to target documentation platforms
- Understanding of the topic area
- Time allocated for thorough research

## Steps

1. **Define Research Scope**
   - Clearly identify the specific topic or question
   - Determine the target audience for the documentation
   - Set boundaries for what will and won't be covered
   - Establish success criteria for the research

2. **Initial Research Phase (Brave Search)**
   - **Use Brave Search first** to research current best practices for your goals
   - Search for framework comparisons, "best [technology] for [use case] 2025"
   - Research community recommendations and recent trends
   - Identify the most current and recommended approaches
   - Gather broad context about available options
   - Note which frameworks/tools are most recommended

3. **Deep Dive Research (Puppeteer)**
   - Use Puppeteer to extract detailed information from official sources
   - Navigate to specific documentation pages and APIs
   - Capture screenshots of important interfaces or examples
   - Extract code examples and configuration details
   - Verify information found in Brave Search

4. **Framework Documentation (Context7 - if needed)**
   - **After choosing specific frameworks/libraries**: Use Context7 for latest official docs
   - Get current syntax, best practices, and migration guides
   - Focus on implementation details for chosen technologies
   - Cross-reference with research findings for consistency

4. **Cross-Reference and Validate**
   - Compare information across multiple authoritative sources
   - Verify technical details through official documentation
   - Test any code examples or procedures if possible
   - Note the currency of information (when it was last updated)

5. **Organize Findings**
   - Structure information logically for the target audience
   - Create clear headings and sections
   - Organize code examples and screenshots
   - Prepare citations and source references

6. **Create Documentation**
   - Write clear, concise content based on research
   - Include practical examples and use cases
   - Add proper citations and source links
   - Structure content for easy navigation and understanding

7. **Review and Verify**
   - Double-check all technical details and examples
   - Verify all links and references work correctly
   - Ensure content meets the defined success criteria
   - Consider having someone else review for clarity

## Success Criteria
- All technical information is accurate and current
- Sources are properly cited and authoritative
- Content is clear and actionable for the target audience
- Examples and procedures have been verified
- Documentation follows established style guidelines

## Troubleshooting

### Research Yields Conflicting Information
- Prioritize official documentation over third-party sources
- Check publication dates to identify most current information
- Look for version-specific differences that might explain conflicts
- When in doubt, note the discrepancy and cite multiple sources

### Limited or Outdated Information
- Check for newer versions or alternative approaches
- Look for community discussions or forums for recent insights
- Consider reaching out to maintainers or experts
- Document the limitations and date of available information

### Technical Examples Don't Work
- Verify you're using the correct versions and dependencies
- Check for environment-specific requirements
- Look for errata or known issues in official documentation
- Test in a clean environment to rule out local configuration issues
