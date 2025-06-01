# Validate Documentation Workflow

This workflow helps you validate and update existing documentation to ensure accuracy and completeness.

## Prerequisites
- Brave Search MCP server configured
- Puppeteer MCP server configured
- Documentation file to validate

## Workflow Steps

### 1. Identify Content to Validate

**Review the documentation and identify:**
- Technical claims that need verification
- External links that should be checked
- Code examples that should be tested
- Information that might be outdated

### 2. Verify External Links

**For each external link, use Puppeteer to check accessibility:**

```xml
<use_mcp_tool>
<server_name>puppeteer</server_name>
<tool_name>puppeteer_navigate</tool_name>
<arguments>
{
  "url": "[link URL]"
}
</arguments>
</use_mcp_tool>
```
**Check if the page loads successfully and content is still relevant.**

### 3. Fact-Check Technical Claims

**For each technical claim, search for current information:**

```xml
<use_mcp_tool>
<server_name>brave-search</server_name>
<tool_name>brave_web_search</tool_name>
<arguments>
{
  "query": "[specific claim] official documentation 2024 2025",
  "count": 5
}
</arguments>
</use_mcp_tool>
```
### 4. Update Outdated Information

**When you find outdated information:**
1. Research the current correct information
2. Update the documentation
3. Add a note about when it was last verified
4. Update any related examples or instructions

### 5. Test Code Examples

**For any code examples or instructions:**
1. Try to follow the steps exactly as written
2. Note any issues or missing steps
3. Update examples to work with current versions
4. Add version information where relevant

### 6. Document Validation Results

**Create a validation report:**


# Validation Report: [Document Name]

## Date: [Current Date]
## Validator: [Your Name]

## Items Checked
- [ ] External links (X working, Y broken)
- [ ] Technical claims (X verified, Y updated)
- [ ] Code examples (X working, Y fixed)
- [ ] Version information (X current, Y updated)

## Issues Found
1. **[Issue Description]**
   - Location: [Section/Line]
   - Problem: [What was wrong]
   - Resolution: [How it was fixed]

## Recommendations
- [Suggestion 1]
- [Suggestion 2]

## Next Review Date
[Date 3 months from now]
```
This workflow ensures documentation stays current and accurate over time.
