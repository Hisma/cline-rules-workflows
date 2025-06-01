# Setup MCP Servers Workflow

## Overview

This workflow guides you through setting up and configuring Model Context Protocol (MCP) servers for effective use with Cline. MCP servers extend Cline's capabilities by providing access to external tools and resources.

## When to Use

- When setting up a new development environment
- When starting a new project that requires MCP capabilities
- When troubleshooting MCP server issues
- When updating or reconfiguring MCP servers
- When adding new MCP servers to your environment

## Prerequisites

- Node.js installed (v14 or higher)
- npm or yarn package manager
- Internet connection
- Appropriate permissions to install packages
- Cline application installed and configured

## Essential MCP Servers

### 1. Context7

**Purpose**: Provides access to framework documentation and API references.

**Installation**:

```bash
# Install Context7 MCP server
npx -y @upstash/context7-mcp@latest
```

**Configuration**:

- No additional configuration required
- Server runs on demand when queried

**Verification**:

```bash
# Verify Context7 is working
npx -y @upstash/context7-mcp@latest --verify
```

### 2. Brave Search

**Purpose**: Enables web research and fact-checking capabilities.

**Installation**:

```bash
# Install Brave Search MCP server
npx -y @modelcontextprotocol/server-brave-search
```

**Configuration**:

- API key is managed automatically
- No additional configuration required

**Verification**:

```bash
# Verify Brave Search is working
npx -y @modelcontextprotocol/server-brave-search --verify
```

### 3. Puppeteer

**Purpose**: Provides content extraction and web automation capabilities.

**Installation**:

```bash
# Install Puppeteer MCP server
npx -y @modelcontextprotocol/server-puppeteer
```

**Configuration**:

- No additional configuration required
- Server runs on demand when queried

**Verification**:

```bash
# Verify Puppeteer is working
npx -y @modelcontextprotocol/server-puppeteer --verify
```

## Additional Useful MCP Servers

### 4. Filesystem

**Purpose**: Provides access to the filesystem for reading and writing files.

**Installation**:

```bash
# Install Filesystem MCP server
npx -y @modelcontextprotocol/server-filesystem [allowed directories]
```

**Configuration**:

- Specify allowed directories as arguments
- Example: `npx -y @modelcontextprotocol/server-filesystem /path/to/project /path/to/data`

**Verification**:

```bash
# Verify Filesystem is working
npx -y @modelcontextprotocol/server-filesystem --verify
```

### 5. Stagehand

**Purpose**: Advanced browser automation for complex web interactions.

**Installation**:

```bash
# Install Stagehand MCP server
npx -y @modelcontextprotocol/server-stagehand
```

**Configuration**:

- No additional configuration required
- Server runs on demand when queried

**Verification**:

```bash
# Verify Stagehand is working
npx -y @modelcontextprotocol/server-stagehand --verify
```

### 6. Excel

**Purpose**: Provides Excel file manipulation capabilities.

**Installation**:

```bash
# Install Excel MCP server
npx -y @negokaz/excel-mcp-server
```

**Configuration**:

- No additional configuration required
- Server runs on demand when queried

**Verification**:

```bash
# Verify Excel MCP server is working
npx -y @negokaz/excel-mcp-server --verify
```

## Setup Process

### 1. Environment Preparation

- **Check Node.js Version**:

```bash
node --version
```

- **Update Node.js** (if needed):

```bash
# Using nvm (recommended)
nvm install --lts

# Or download from nodejs.org
```

- **Check npm Version**:

```bash
npm --version
```

### 2. Install Essential MCP Servers

```bash
# Install all essential MCP servers
npx -y @upstash/context7-mcp@latest
npx -y @modelcontextprotocol/server-brave-search
npx -y @modelcontextprotocol/server-puppeteer
```

### 3. Verify Installation

- **Check Running Servers**:

```bash
# List running MCP servers
ps aux | grep mcp
```

- **Test with Cline**:

1. Open Cline
2. Ask a question that requires MCP capabilities
3. Verify Cline can access and use the MCP servers

### 4. Troubleshooting

- **Server Not Starting**:

```bash
# Check for port conflicts
lsof -i :[port number]

# Kill conflicting process
kill [process id]
```

- **Permission Issues**:

```bash
# Run with elevated permissions (if needed)
sudo npx -y @modelcontextprotocol/server-[name]
```

- **Dependency Issues**:

```bash
# Clear npm cache
npm cache clean --force

# Reinstall server
npx -y @modelcontextprotocol/server-[name]
```

## MCP Server Usage

### Context7 Usage

```text
# Example Context7 Query
"Get documentation for React useState hook"
"Find information about Express.js routing"
"Look up MongoDB aggregation pipeline documentation"
```

### Brave Search Usage

```text
# Example Brave Search Query
"Latest news about artificial intelligence"
"Best practices for React performance optimization 2024"
"How to implement authentication in Node.js"
```

### Puppeteer Usage

```text
# Example Puppeteer Commands
"Extract content from https://example.com"
"Take a screenshot of https://example.com"
"Click the login button on https://example.com"
```

## Best Practices

### Performance Optimization

- **Run Servers On-Demand**:

```bash
# Start server only when needed
npx -y @modelcontextprotocol/server-[name]

# Stop when finished
# (Press Ctrl+C in the terminal window)
```

- **Resource Management**:

```bash
# Set resource limits (example for Puppeteer)
NODE_OPTIONS="--max-old-space-size=4096" npx -y @modelcontextprotocol/server-puppeteer
```

### Security Considerations

- **Filesystem Access**: Limit filesystem access to specific directories
- **API Keys**: Secure any API keys used by MCP servers
- **Network Access**: Be aware of network access by MCP servers
- **Content Extraction**: Be mindful of terms of service when extracting content

### Maintenance

- **Regular Updates**:

```bash
# Update all MCP servers
npx -y @upstash/context7-mcp@latest
npx -y @modelcontextprotocol/server-brave-search@latest
npx -y @modelcontextprotocol/server-puppeteer@latest
```

- **Monitoring**:

```bash
# Monitor server logs
npx -y @modelcontextprotocol/server-[name] --verbose
```

## Advanced Configuration

### Running as Services

- **Using PM2**:

```bash
# Install PM2
npm install -g pm2

# Start MCP server with PM2
pm2 start "npx -y @modelcontextprotocol/server-[name]" --name "mcp-[name]"

# List running services
pm2 list

# Stop service
pm2 stop "mcp-[name]"
```

### Custom Port Configuration

- **Setting Custom Ports**:

```bash
# Run on specific port
PORT=3001 npx -y @modelcontextprotocol/server-[name]
```

### Environment Variables

- **Common Environment Variables**:

```bash
# Debug mode
DEBUG=true npx -y @modelcontextprotocol/server-[name]

# Verbose logging
VERBOSE=true npx -y @modelcontextprotocol/server-[name]

# Custom configuration path
CONFIG_PATH=/path/to/config.json npx -y @modelcontextprotocol/server-[name]
```

## Troubleshooting Guide

### Common Issues

- **Server Crashes**:
  - Check system resources (memory, CPU)
  - Update to latest version
  - Check for conflicting processes

- **Connection Refused**:
  - Verify server is running
  - Check port availability
  - Check firewall settings

- **Timeout Errors**:
  - Increase timeout settings
  - Check network connectivity
  - Verify server resources

### Diagnostic Commands

```bash
# Check if server is running
ps aux | grep mcp

# Check port usage
lsof -i :[port number]

# Check system resources
top

# Check logs
npx -y @modelcontextprotocol/server-[name] --verbose
```

## Notes

- MCP servers extend Cline's capabilities significantly
- Different projects may require different MCP servers
- Keep servers updated for best performance and security
- Consider resource usage when running multiple servers
- Some servers may require API keys or additional configuration

**Remember**: MCP servers provide powerful capabilities to Cline, but they also consume system resources. Run only the servers you need for your current task.
