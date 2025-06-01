# Technology Stack

## Framework Verification

**Last Verified**: 2025-05-31
**Verification Method**: Brave Search + Puppeteer + Context7 (if applicable)
**Next Review**: 2025-06-30

*All frameworks and libraries below have been verified using the [Verify Tech Stack Workflow](../templates/global/Workflows/verify-tech-stack.md)*

## Documentation Format

**Markdown** - Primary documentation format for all content

### Key Libraries

- **Standard Markdown**: CommonMark specification compliance
- **GitHub Flavored Markdown**: Extended syntax for tables, code blocks, task lists
- **Mermaid Diagrams**: For flowcharts, sequence diagrams, and architecture visuals
- **LaTeX Math**: Mathematical expressions and formulas when needed

## Research and Verification Tools

### MCP Servers

- **Brave Search**: Primary research tool for current best practices (see [MCP Server Requirements](../templates/global/Rules/mcp-server-requirements.md))
- **Puppeteer**: Content extraction from official documentation sources
- **Context7**: Framework documentation (not needed for this documentation-only project)

*All MCP servers must be configured before using research workflows*

### Research Methodology

- **Primary Sources**: Official Cline documentation, GitHub repositories, and authoritative sources
- **Cross-Verification**: Multiple source validation for accuracy of Cline features and capabilities
- **Currency Checks**: Regular updates to ensure information reflects current Cline versions
- **Community Validation**: Verification through Cline community feedback and testing

## Development Tools

### Version Control

- **Git**: All documentation versioned and tracked
- **GitHub**: Repository hosting with issue tracking and pull requests
- **Branching Strategy**: Feature branches for major updates, main for stable content

### Content Management

- **File Organization**: Structured directory hierarchy with docs/ and templates/ separation
- **Naming Conventions**: Consistent file and directory naming following template patterns
- **Cross-References**: Internal linking between documentation and template examples

## Quality Assurance

### Validation Tools

- **Link Checking**: Automated verification of external links to Cline documentation
- **Spell Check**: Grammar and spelling validation
- **Markdown Linting**: Consistent formatting and structure
- **Fact Verification**: Regular accuracy reviews using MCP research tools
- **Template Testing**: Verification that templates work as documented

### Review Process

- **Community Feedback**: User testing and feedback incorporation from Cline users
- **Regular Audits**: Monthly content accuracy and completeness reviews
- **Template Validation**: Testing templates with actual Cline implementations

## MCP Integration Patterns

### Brave Search Usage

```text
# Research Pattern for Cline Documentation
1. Search for "Cline rules workflows latest documentation"
2. Verify current Cline version capabilities
3. Cross-reference with official Cline GitHub repository
4. Document search queries and results for reproducibility
```

### Puppeteer Content Extraction

```javascript
// Extract content from Cline documentation
puppeteer_evaluate: "document.querySelector('.documentation-content').innerText"

// Extract version information
puppeteer_evaluate: "document.querySelector('.version-info').innerText"

// Extract feature lists
puppeteer_evaluate: "Array.from(document.querySelectorAll('.feature-list li')).map(li => li.textContent)"
```
### Research Workflow Integration

- **Search First**: Use Brave Search for current Cline capabilities and best practices
- **Verify with Puppeteer**: Extract content from official Cline documentation
- **Document Sources**: Maintain citation trail to official sources
- **Update Regularly**: Monthly re-verification of Cline features and capabilities

## Documentation Standards

### Content Structure

- **Hierarchical Organization**: Clear heading structure (H1-H6)
- **Consistent Templates**: Standardized formats for rules and workflows documentation
- **Cross-References**: Internal linking between docs/ and templates/ directories
- **Code Examples**: Syntax highlighting for Markdown and configuration examples

### Style Guidelines

- **Clear Language**: Accessible to developers new to Cline customization
- **Consistent Terminology**: Standardized vocabulary for rules, workflows, global, and workspace concepts
- **Visual Elements**: Appropriate use of diagrams for directory structures and workflows
- **Actionable Content**: Step-by-step instructions with copy-paste commands

## Collaboration Tools

### Communication

- **GitHub Issues**: Content requests and bug reports for documentation and templates
- **Pull Requests**: Collaborative editing and community contributions
- **Discussions**: Community feedback and template improvement suggestions

### Documentation Maintenance

- **Regular Updates**: Monthly content review cycles aligned with Cline releases
- **Template Evolution**: Quarterly review and update of templates based on community feedback
- **Version History**: Changelog maintenance for template updates
- **Migration Guides**: When template structure changes significantly

## Performance Considerations

### Content Optimization

- **File Size**: Optimized for quick loading and easy navigation
- **Load Times**: Efficient content organization with clear table of contents
- **Search Optimization**: Clear headings and keyword usage for findability
- **Mobile Friendly**: Responsive content design for various devices

### Research Efficiency

- **Cached Results**: Avoid redundant research queries for stable Cline features
- **Batch Operations**: Efficient use of MCP tools for comprehensive updates
- **Source Prioritization**: Focus on official Cline documentation first
- **Update Scheduling**: Strategic timing aligned with Cline release cycles

## Project-Specific Technologies

- **Cline VSCode Extension**: Primary target platform for rules and workflows
- **VSCode**: Development environment where Cline operates
- **Node.js/NPX**: For MCP server installation and management
- **JSON**: Configuration format for MCP server settings

## Notes

- This tech stack is specifically designed for Cline rules and workflows documentation
- Templates are tested with actual Cline implementations
- MCP server integration is considered essential for effective documentation creation
- Regular updates ensure alignment with current Cline capabilities and best practices

This tech stack emphasizes accuracy, maintainability, and practical utility for Cline users while leveraging modern research and verification tools.
