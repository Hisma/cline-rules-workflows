# MCP Server Requirements

This document outlines the required MCP (Model Context Protocol) servers for our rules and workflows system, and provides setup instructions for each.

## Required MCP Servers

Our documentation and development workflows require these MCP servers to be configured in Cline:

### 1. Context7 - Framework Documentation
**Purpose**: Get latest documentation for frameworks, libraries, and APIs
**Required for**: Tech stack verification, framework research, current syntax validation

### 2. Brave Search - Web Research  
**Purpose**: Comprehensive web search for research and fact-checking
**Required for**: Research workflows, documentation verification, current information gathering

### 3. Puppeteer - Web Content Extraction
**Purpose**: Extract content from web pages, take screenshots, interact with websites
**Required for**: Deep research, content verification, web-based testing

## Checking Current MCP Configuration

### 1. Locate Cline MCP Settings
Check your current MCP configuration in:
```
/config/data/User/globalStorage/saoudrizwan.claude-dev/settings/cline_mcp_settings.json
```

### 2. Verify Required Servers
Look for these server entries in the `mcpServers` object:
- `github.com/upstash/context7-mcp`
- `brave-search` 
- `puppeteer` or `github.com/modelcontextprotocol/servers/tree/main/src/puppeteer`

## MCP Server Setup Instructions

### Context7 Setup

**Add to cline_mcp_settings.json:**
```json
{
  "mcpServers": {
    "github.com/upstash/context7-mcp": {
      "autoApprove": [],
      "disabled": false,
      "timeout": 60,
      "command": "npx",
      "args": [
        "-y",
        "@upstash/context7-mcp@latest"
      ],
      "transportType": "stdio"
    }
  }
}
```

**No additional configuration required** - Context7 works out of the box.

### Brave Search Setup

**Add to cline_mcp_settings.json:**
```json
{
  "mcpServers": {
    "brave-search": {
      "timeout": 60,
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-brave-search"
      ],
      "env": {
        "BRAVE_API_KEY": "YOUR_BRAVE_API_KEY_HERE"
      },
      "transportType": "stdio"
    }
  }
}
```

**API Key Required:**
1. Go to [Brave Search API](https://api.search.brave.com/)
2. Sign up for a free account
3. Get your API key
4. Replace `YOUR_BRAVE_API_KEY_HERE` with your actual API key

### Puppeteer Setup

**Add to cline_mcp_settings.json:**
```json
{
  "mcpServers": {
    "puppeteer": {
      "timeout": 60,
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-puppeteer"
      ],
      "env": {
        "PUPPETEER_LAUNCH_OPTIONS": "{ \"headless\": true, \"args\": [\"--no-sandbox\", \"--disable-setuid-sandbox\"] }",
        "ALLOW_DANGEROUS": "true"
      },
      "transportType": "stdio"
    }
  }
}
```

**No API key required** - Works with the configuration above.

## Complete Configuration Example

Here's a complete example of the required MCP servers in your settings file:

```json
{
  "mcpServers": {
    "github.com/upstash/context7-mcp": {
      "autoApprove": [],
      "disabled": false,
      "timeout": 60,
      "command": "npx",
      "args": [
        "-y",
        "@upstash/context7-mcp@latest"
      ],
      "transportType": "stdio"
    },
    "brave-search": {
      "timeout": 60,
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-brave-search"
      ],
      "env": {
        "BRAVE_API_KEY": "YOUR_BRAVE_API_KEY_HERE"
      },
      "transportType": "stdio"
    },
    "puppeteer": {
      "timeout": 60,
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-puppeteer"
      ],
      "env": {
        "PUPPETEER_LAUNCH_OPTIONS": "{ \"headless\": true, \"args\": [\"--no-sandbox\", \"--disable-setuid-sandbox\"] }",
        "ALLOW_DANGEROUS": "true"
      },
      "transportType": "stdio"
    }
  }
}
```

## Verification Steps

### 1. Restart Cline
After adding MCP servers, restart Cline to load the new configuration.

### 2. Test Each MCP Server

**Test Context7:**
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

**Test Brave Search:**
```xml
<use_mcp_tool>
<server_name>brave-search</server_name>
<tool_name>brave_web_search</tool_name>
<arguments>
{
  "query": "test search",
  "count": 3
}
</arguments>
</use_mcp_tool>
```

**Test Puppeteer:**
```xml
<use_mcp_tool>
<server_name>puppeteer</server_name>
<tool_name>puppeteer_navigate</tool_name>
<arguments>
{
  "url": "https://example.com"
}
</arguments>
</use_mcp_tool>
```

## Troubleshooting

### MCP Server Not Found
- Check spelling of server name in configuration
- Ensure JSON syntax is correct
- Restart Cline after configuration changes

### API Key Issues
- Verify API key is correct and active
- Check that environment variables are properly set
- Ensure no extra spaces or characters in API key

### Connection Timeouts
- Increase timeout value if needed
- Check internet connection
- Verify MCP server package is available

### Permission Issues
- Ensure `ALLOW_DANGEROUS: "true"` is set for Puppeteer
- Check that npx has permission to install packages
- Verify file system permissions for configuration file

## Best Practices

### Security
- Keep API keys secure and don't commit them to version control
- Use environment variables for sensitive configuration
- Regularly rotate API keys

### Performance
- Set appropriate timeout values based on your needs
- Monitor MCP server resource usage
- Consider caching strategies for frequently accessed data

### Maintenance
- Regularly update MCP server packages to latest versions
- Monitor for deprecated MCP servers or APIs
- Keep configuration documentation current

## MCP Server Usage Guidelines

### Research-First Workflow Pattern

**1. Brave Search (Primary Research)**
- **When**: Start of any project or research task
- **Purpose**: Research current best practices, framework comparisons, community recommendations
- **Use for**: "Best [technology] for [use case] 2025", framework comparisons, trend analysis
- **Priority**: High - essential for research-driven development

**2. Puppeteer (Content Extraction)**
- **When**: After Brave Search identifies authoritative sources
- **Purpose**: Extract detailed content from official documentation sites
- **Use for**: Getting specific details, code examples, screenshots from official sources
- **Priority**: High - essential for thorough research workflows

**3. Context7 (Framework Documentation)**
- **When**: After choosing specific frameworks/libraries from research
- **Purpose**: Get latest official documentation for chosen technologies
- **Use for**: Current syntax, migration guides, best practices for specific frameworks
- **Priority**: Medium - only needed for projects using supported frameworks

### When NOT to Use Each Tool

**Don't use Context7 for:**
- Initial research or framework selection
- General topic research
- Simple projects without complex frameworks

**Don't use Brave Search + Puppeteer for:**
- Getting documentation for frameworks you've already chosen
- Redundant verification when Context7 has current information

### Project Type Guidelines

**Complex Framework Projects (React, Vue, Express, etc.):**
1. Brave Search → Research best approaches
2. Puppeteer → Extract details from official sources
3. Context7 → Get latest framework documentation

**Simple Projects (HTML/CSS, documentation sites):**
1. Brave Search → Research best practices
2. Puppeteer → Extract examples and details
3. Skip Context7 (not needed)

**Research Projects:**
1. Brave Search → Primary research tool
2. Puppeteer → Content extraction
3. Context7 → Only if researching specific frameworks

## Integration with Workflows

Once MCP servers are configured, they enable:
- **Research-driven documentation** with current, verified information
- **Framework verification** using latest official documentation
- **Comprehensive fact-checking** for all technical content
- **Automated content extraction** from authoritative sources

All workflows in this repository assume these MCP servers are properly configured and will fail gracefully with clear error messages if they're not available.
