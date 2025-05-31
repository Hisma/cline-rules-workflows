# Technology Stack

## Framework Verification
**Last Verified**: [Date - Update when tech stack is verified]
**Verification Method**: Brave Search + Puppeteer + Context7 (if applicable)
**Next Review**: [Date - Schedule monthly reviews]

*All frameworks and libraries below have been verified using the [Verify Tech Stack Workflow](../global/workflows/verify-tech-stack.md)*

## Documentation Format
**Markdown** - Primary documentation format for all content

### Key Libraries
- **Standard Markdown**: CommonMark specification compliance
- **GitHub Flavored Markdown**: Extended syntax for tables, code blocks, task lists
- **Mermaid Diagrams**: For flowcharts, sequence diagrams, and architecture visuals
- **LaTeX Math**: Mathematical expressions and formulas when needed
- **[Add project-specific markdown extensions]**

## Research and Verification Tools

### MCP Servers
- **Brave Search**: Primary research tool for current best practices (see [MCP Server Requirements](../global/rules/mcp-server-requirements.md))
- **Puppeteer**: Content extraction from official documentation sources
- **Context7**: Framework documentation (only needed if using complex frameworks - often not needed for documentation sites)

*All MCP servers must be configured before using research workflows*
- **[Add other MCP servers as needed]**

### Research Methodology
- **Primary Sources**: Official documentation, specifications, and authoritative sources
- **Cross-Verification**: Multiple source validation for accuracy
- **Currency Checks**: Regular updates to ensure information remains current
- **[Add project-specific research approaches]**

## Development Tools

### Version Control
- **Git**: All documentation versioned and tracked
- **GitHub**: Repository hosting with issue tracking and pull requests
- **Branching Strategy**: Feature branches for major updates, main for stable content
- **[Customize based on your workflow]**

### Content Management
- **File Organization**: Structured directory hierarchy
- **Naming Conventions**: Consistent file and directory naming
- **Cross-References**: Internal linking and reference management
- **[Add project-specific organization patterns]**

## Static Site Generation (if applicable)
- **[Site Generator]**: [Jekyll, Hugo, Sphinx, etc.]
- **Theme**: [Theme name and customizations]
- **Build Process**: [Description of build and deployment]
- **Hosting**: [GitHub Pages, Netlify, etc.]

## Quality Assurance

### Validation Tools
- **Link Checking**: Automated verification of external links
- **Spell Check**: Grammar and spelling validation
- **Markdown Linting**: Consistent formatting and structure
- **Fact Verification**: Regular accuracy reviews using research tools
- **[Add project-specific QA tools]**

### Review Process
- **Peer Review**: Subject matter expert validation
- **Community Feedback**: User testing and feedback incorporation
- **Regular Audits**: Scheduled content accuracy and completeness reviews
- **[Customize review workflow]**

## MCP Integration Patterns

### Brave Search Usage
```markdown
# Research Pattern
1. Initial broad search for topic overview
2. Targeted searches for specific technical details
3. Cross-reference multiple authoritative sources
4. Document search queries and results for reproducibility
```

### Puppeteer Content Extraction
```javascript
// Standard pattern for extracting page content
puppeteer_evaluate: "document.body.innerText"

// For specific content sections
puppeteer_evaluate: "document.querySelector('.documentation').innerText"

// For structured data extraction
puppeteer_evaluate: "Array.from(document.querySelectorAll('h2')).map(h => h.textContent)"
```

### Research Workflow Integration
- **Search First**: Use Brave Search for initial research
- **Verify with Puppeteer**: Extract content from official sources
- **Document Sources**: Maintain citation trail
- **Update Regularly**: Scheduled re-verification of facts

## Documentation Standards

### Content Structure
- **Hierarchical Organization**: Clear heading structure (H1-H6)
- **Consistent Templates**: Standardized formats for different content types
- **Cross-References**: Internal and external linking strategies
- **Code Examples**: Syntax highlighting and executable examples

### Style Guidelines
- **Clear Language**: Accessible to target audience
- **Consistent Terminology**: Standardized vocabulary and definitions
- **Visual Elements**: Appropriate use of diagrams, tables, and lists
- **Actionable Content**: Step-by-step instructions and examples

## Collaboration Tools

### Communication
- **Issue Tracking**: GitHub Issues for content requests and bug reports
- **Pull Requests**: Collaborative editing and review process
- **Discussions**: Community feedback and improvement suggestions
- **[Add project-specific collaboration tools]**

### Documentation Maintenance
- **Regular Updates**: Scheduled content review cycles
- **Deprecation Notices**: Clear marking of outdated information
- **Version History**: Changelog maintenance and release notes
- **Migration Guides**: When content structure changes significantly

## Performance Considerations

### Content Optimization
- **File Size**: Optimized images and media
- **Load Times**: Efficient content organization
- **Search Optimization**: Clear headings and keyword usage
- **Mobile Friendly**: Responsive content design

### Research Efficiency
- **Cached Results**: Avoid redundant research queries
- **Batch Operations**: Efficient use of MCP tools
- **Source Prioritization**: Focus on most authoritative sources first
- **Update Scheduling**: Strategic timing for content refreshes

## Project-Specific Technologies
- **[Technology 1]**: [Description and usage]
- **[Technology 2]**: [Description and usage]
- **[Add other relevant technologies]**

## Notes
- Customize this tech stack based on your specific documentation project
- Remove sections that don't apply to your project
- Add technologies and tools specific to your domain
- Update regularly as your tech stack evolves

This tech stack emphasizes accuracy, maintainability, and collaborative documentation creation while leveraging modern research and verification tools.
