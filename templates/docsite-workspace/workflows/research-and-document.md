# Research and Document Workflow

## Overview

This workflow provides a systematic approach to researching topics and creating high-quality documentation using MCP servers. It ensures accuracy, completeness, and proper citation of sources.

## When to Use

- Creating new documentation from scratch
- Updating existing content with current information
- Researching best practices and current standards
- Fact-checking existing documentation
- Preparing comprehensive guides or tutorials

## Prerequisites

- [ ] MCP servers are configured and active:
  - Brave Search (for web research)
  - Puppeteer (for content extraction)
  - Context7 (for framework documentation, if applicable)
- [ ] Markdown linting is set up (`.markdownlint.json` exists)
- [ ] Clear research objectives defined

## Research Process

### Phase 1: Research Planning

**Step 1: Define Research Scope**

- [ ] Identify specific topics to research
- [ ] Define target audience and use cases
- [ ] Establish success criteria for the documentation
- [ ] Set timeline and milestones

**Step 2: Prepare Research Framework**

```text
# Research Template
## Topic: [Topic Name]
## Objective: [What you want to achieve]
## Target Audience: [Who will use this information]
## Key Questions
- [Question 1]
- [Question 2]
- [Question 3]

## Sources to Investigate
- Official documentation
- Community resources
- Best practice guides
- Recent updates/changes
```

### Phase 2: Primary Research

**Step 3: Web Research with Brave Search**

Use Brave Search MCP server for comprehensive web research:

```text
# Search Strategy
1. Start with broad searches: "[Topic] best practices 2024"
2. Narrow to specific aspects: "[Topic] setup guide"
3. Look for official sources: "[Topic] official documentation"
4. Check for recent updates: "[Topic] latest changes"
```

Research checklist:

- [ ] Search for official documentation and guides
- [ ] Find current best practices and standards
- [ ] Identify common issues and solutions
- [ ] Look for recent updates or changes
- [ ] Gather community insights and feedback

**Step 4: Content Extraction with Puppeteer**

Use Puppeteer MCP server to extract detailed content:

```javascript
// Example extraction patterns
// Extract main content
puppeteer_evaluate: "document.querySelector('main').innerText"

// Extract code examples
puppeteer_evaluate: "Array.from(document.querySelectorAll('pre code')).map(el => el.textContent)"

// Extract headings for structure
puppeteer_evaluate: "Array.from(document.querySelectorAll('h1, h2, h3')).map(h => ({level: h.tagName, text: h.textContent}))"
```

Extraction checklist:

- [ ] Extract key concepts and definitions
- [ ] Gather code examples and configurations
- [ ] Collect step-by-step procedures
- [ ] Note version requirements and compatibility
- [ ] Document source URLs and access dates

**Step 5: Framework Documentation (Context7)**

If applicable, use Context7 for framework-specific research:

- [ ] Search for relevant framework documentation
- [ ] Extract API references and examples
- [ ] Gather integration patterns
- [ ] Note version-specific information

## Phase 3: Information Synthesis

**Step 6: Organize Research Findings**

```text
# Research Summary Template
## Key Findings
- [Finding 1 with source]
- [Finding 2 with source]
- [Finding 3 with source]

## Best Practices Identified
1. [Practice 1] - Source: [URL]
2. [Practice 2] - Source: [URL]
3. [Practice 3] - Source: [URL]

## Common Issues and Solutions
- **Issue**: [Description]
  **Solution**: [Solution with source]

## Version/Compatibility Notes
- [Technology] version [X.X] and above
- Compatible with [Platform/Tool]
- Known issues with [Specific versions]
```

**Step 7: Fact Verification**

Cross-reference findings across multiple sources:

- [ ] Verify information against official documentation
- [ ] Check for consistency across sources
- [ ] Identify any conflicting information
- [ ] Note areas requiring further research

**Step 8: Gap Analysis**

- [ ] Identify missing information
- [ ] Note areas needing additional research
- [ ] Plan follow-up research if needed
- [ ] Document assumptions and limitations

### Phase 4: Documentation Creation

**Step 9: Structure Planning**

```text
# Documentation Outline
1. Overview/Introduction
2. Prerequisites
3. Step-by-Step Instructions
4. Examples and Use Cases
5. Troubleshooting
6. Additional Resources
7. References and Sources
```

**Step 10: Content Creation**

Follow markdown standards (see [Markdown Standards](../rules/05-markdown-standards.md)):

- [ ] Use proper heading hierarchy
- [ ] Specify languages for all code blocks
- [ ] Include clear, actionable instructions
- [ ] Provide practical examples
- [ ] Add troubleshooting guidance

**Step 11: Source Citation**

```text
# Citation Format
## References
- [Source Title](URL) - Accessed [Date]
- [Official Documentation](URL) - Version [X.X]
- [Community Guide](URL) - Last Updated [Date]

## Research Notes
- Research conducted: [Date]
- MCP servers used: Brave Search, Puppeteer, Context7
- Primary sources: [List key sources]
```

### Phase 5: Quality Assurance

**Step 12: Content Review**

- [ ] Verify all information is current and accurate
- [ ] Test all code examples and procedures
- [ ] Check that instructions are clear and complete
- [ ] Ensure proper markdown formatting

**Step 13: Markdown Validation**

```bash
# Run markdown linting
markdownlint "path/to/new-document.md"

# Fix any issues
markdownlint "path/to/new-document.md" --fix
```

**Step 14: Link Verification**

```bash
# Check external links
markdown-link-check "path/to/new-document.md"
```

- [ ] All external links are functional
- [ ] Internal references are correct
- [ ] Sources are properly cited

### Phase 6: Publication and Maintenance

**Step 15: Integration**

- [ ] Add to appropriate documentation structure
- [ ] Update navigation and cross-references
- [ ] Link from relevant existing documents
- [ ] Update table of contents if applicable

**Step 16: Version Control**

```bash
# Add new documentation
git add path/to/new-document.md

# Commit with descriptive message
git commit -m "Add comprehensive guide for [Topic] based on MCP research"
```

**Step 17: Maintenance Planning**

- [ ] Set review schedule (monthly/quarterly)
- [ ] Document research methodology for future updates
- [ ] Note areas requiring regular verification
- [ ] Plan for technology updates and changes

## Research Quality Checklist

### Source Quality

- [ ] Official documentation consulted
- [ ] Multiple sources cross-referenced
- [ ] Recent/current information prioritized
- [ ] Community feedback considered

### Content Quality

- [ ] Information is accurate and current
- [ ] Instructions are clear and actionable
- [ ] Examples are practical and tested
- [ ] Troubleshooting guidance provided

### Technical Quality

- [ ] Markdown standards followed
- [ ] All links functional
- [ ] Code examples properly formatted
- [ ] Proper citation of sources

## MCP Server Usage Patterns

### Brave Search Strategies

```text
# Effective Search Patterns
- "[Technology] official documentation"
- "[Technology] best practices [current year]"
- "[Technology] setup guide tutorial"
- "[Technology] common issues solutions"
- "[Technology] vs alternatives comparison"
```

## Puppeteer Extraction Patterns

```javascript
// Common extraction patterns
// Get all text content
document.body.innerText

// Extract specific sections
document.querySelector('.documentation-content').innerHTML

// Get code examples
Array.from(document.querySelectorAll('pre')).map(pre => pre.textContent)

// Extract navigation structure
Array.from(document.querySelectorAll('nav a')).map(a => ({text: a.textContent, href: a.href}))
```

## Troubleshooting

### Research Issues

**Limited Information Available**

- Expand search terms and strategies
- Look for related technologies or concepts
- Check community forums and discussions
- Consider reaching out to experts

**Conflicting Information**

- Prioritize official sources
- Check publication dates for currency
- Look for consensus across multiple sources
- Document conflicts and note preferred approach

**Technical Examples Don't Work**

- Verify version compatibility
- Check for missing dependencies
- Test in clean environment
- Document any modifications needed

### MCP Server Issues

**Search Results Not Relevant**

- Refine search terms
- Use more specific queries
- Try different search strategies
- Combine multiple searches

**Content Extraction Incomplete**

- Try different CSS selectors
- Extract in smaller chunks
- Use multiple extraction approaches
- Manually supplement if needed

## Success Metrics

- [ ] All research objectives met
- [ ] Documentation is comprehensive and accurate
- [ ] Sources properly cited and current
- [ ] Content passes all quality checks
- [ ] User feedback is positive
- [ ] Information remains current over time

## Notes

- This workflow emphasizes research-driven development
- MCP servers are essential for current, accurate information
- Regular updates ensure documentation remains valuable
- Proper citation builds credibility and enables verification
- Quality standards ensure professional, useful documentation

**Remember**: The goal is to create accurate, comprehensive, and useful documentation that serves users effectively while maintaining high standards for quality and currency.
