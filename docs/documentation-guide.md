# Create Documentation Workflow

## Overview

This workflow guides you through the process of creating high-quality documentation for your project. It provides step-by-step instructions for planning, researching, writing, reviewing, and publishing documentation.

## When to Use

- When starting documentation for a new project
- When updating existing documentation
- When creating user guides, API documentation, or technical references
- When standardizing documentation across a team
- When improving documentation quality and consistency

## Workflow Steps

### Step 1: Define Documentation Scope

**Actions:**
1. Identify the documentation purpose and goals
2. Define the target audience and their needs
3. Determine what topics need to be covered
4. Establish documentation success criteria
5. Create a documentation plan with timeline

**Output:** Documentation plan document with scope, audience, topics, and timeline

### Step 2: Research and Gather Information

**Actions:**
1. Collect existing documentation and information
2. Interview subject matter experts
3. Research similar documentation for inspiration
4. Use MCP servers to gather current best practices
5. Document key findings and information gaps

**Tools:**
- Brave Search MCP for web research
- Context7 MCP for framework documentation
- Puppeteer MCP for content extraction

### Step 3: Create Documentation Structure

**Actions:**
1. Choose appropriate documentation templates
2. Create a logical outline with sections and subsections
3. Plan information flow from basic to advanced topics
4. Establish consistent formatting patterns
5. Set up navigation and cross-references

**Templates:**
- Project Overview: `/templates/documentation-templates/project-overview.md`
- Tech Stack: `/templates/documentation-templates/tech-stack.md`
- Architecture: `/templates/documentation-templates/architecture.md`
- Requirements: `/templates/documentation-templates/current-requirements.md`

### Step 4: Write Documentation Content

**Actions:**
1. Write clear, concise content following the outline
2. Include practical examples and code snippets
3. Add diagrams and visual aids where helpful
4. Follow markdown standards for formatting
5. Use consistent terminology and style

**Standards:**
- Use active voice and present tense
- Specify language for all code blocks
- Include step-by-step instructions for procedures
- Provide context and explanations, not just commands
- Use headings, lists, and formatting for readability

### Step 5: Add Visual Elements

**Actions:**
1. Create diagrams for complex concepts
2. Add screenshots for UI elements
3. Include flowcharts for processes
4. Create tables for comparing options
5. Ensure all visuals have alt text and captions

**Tools:**
- Mermaid for diagrams and flowcharts
- Screenshots with annotations
- Tables in markdown format
- Consistent styling for all visuals

### Step 6: Review and Refine

**Actions:**
1. Perform self-review for clarity and completeness
2. Conduct technical review for accuracy
3. Get peer feedback on usability and clarity
4. Run markdown linting to check formatting
5. Verify all links and references

**Checklist:**
- [ ] Content is technically accurate
- [ ] Instructions work as described
- [ ] All links are functional
- [ ] Markdown is correctly formatted
- [ ] Content flows logically

### Step 7: Publish and Maintain

**Actions:**
1. Finalize documentation and commit to repository
2. Announce documentation to stakeholders
3. Gather initial feedback and make adjustments
4. Establish maintenance schedule
5. Plan for regular updates and improvements

**Maintenance:**
- Schedule regular reviews (monthly/quarterly)
- Update when features or processes change
- Track feedback and improvement ideas
- Version documentation alongside code

## Documentation Types and Templates

### Project Documentation

Use these templates as starting points:

**Project Overview**
- Template: `/templates/documentation-templates/project-overview.md`
- Purpose: Describe project goals, audience, and features
- When to create: At project start, update quarterly

**Tech Stack**
- Template: `/templates/documentation-templates/tech-stack.md`
- Purpose: Document technologies, frameworks, and tools
- When to create: At project start, update when stack changes

**Architecture**
- Template: `/templates/documentation-templates/architecture.md`
- Purpose: Explain system structure and components
- When to create: During initial design, update with major changes

**Requirements**
- Template: `/templates/documentation-templates/current-requirements.md`
- Purpose: Track current priorities and features
- When to create: At project start, update monthly

### Code Documentation

**API Documentation**
- Purpose: Document endpoints, parameters, and responses
- When to create: As APIs are developed, update with changes
- Format: Include examples, error responses, and authentication

**Function/Class Documentation**
- Purpose: Explain purpose, parameters, and return values
- When to create: As code is written, update with changes
- Format: Include examples, edge cases, and usage notes

### User Documentation

**User Guides**
- Purpose: Provide step-by-step instructions
- When to create: Before release to users
- Format: Task-based organization with screenshots

**Tutorials**
- Purpose: Teach users how to accomplish specific goals
- When to create: For common or complex user tasks
- Format: Step-by-step with examples and explanations

## Documentation Quality Checklist

### Content Quality

- [ ] Information is accurate and current
- [ ] All necessary topics are covered
- [ ] Content is appropriate for the audience
- [ ] Examples are relevant and helpful
- [ ] No unnecessary information is included

### Structure Quality

- [ ] Logical organization of content
- [ ] Clear headings and subheadings
- [ ] Appropriate use of lists and tables
- [ ] Consistent formatting throughout
- [ ] Progressive disclosure of complex topics

### Technical Quality

- [ ] All code examples work as described
- [ ] All links are functional
- [ ] Images are clear and properly sized
- [ ] Markdown is correctly formatted
- [ ] No spelling or grammatical errors

### User Experience

- [ ] Content is easy to navigate
- [ ] Information is easy to find
- [ ] Documentation answers likely questions
- [ ] Reading flow is logical and smooth
- [ ] Documentation is accessible to all users

## Writing Guidelines

### Clear and Concise Writing

- Use active voice: "The function returns a value" not "A value is returned"
- Be concise: Eliminate unnecessary words
- Use present tense: "The API returns..." not "The API will return..."
- Write directly to the reader: Use "you" instead of "the user"
- Avoid jargon: Define technical terms when necessary

### Effective Formatting

- Use headings to organize content (H1 for title, H2 for major sections, etc.)
- Use bullet points for lists of items
- Use numbered lists for sequential steps
- Use code blocks with language specification
- Use tables for comparing options or parameters

### Common Documentation Patterns

**Procedures:**
```markdown
## How to [Task Name]

1. First step
   - Additional details
   - Optional variations
2. Second step
   - Expected results
   - Troubleshooting tips
3. Third step
   - Verification steps
   - Next steps
```

**Concepts:**
```markdown
## [Concept Name]

[Definition and purpose]

### Key Components
- [Component 1]: [Description]
- [Component 2]: [Description]

### Examples
```

**Reference:**
```markdown
## [Function/API Name]

**Purpose**: [Brief description]

**Parameters**:
- `param1` (type): Description
- `param2` (type): Description

**Returns**: [Return value description]

**Example**:
```code
[Example code]
```

## Tools and Resources

### Documentation Tools

- **Markdown Editors**: VS Code, Typora
- **Diagram Tools**: Mermaid, Draw.io, Lucidchart
- **Screenshot Tools**: Snagit, Greenshot
- **Linters**: markdownlint, vale
- **Version Control**: Git for documentation versioning

### MCP Server Usage

- **Brave Search**: Research current best practices and standards
- **Context7**: Access framework documentation and examples
- **Puppeteer**: Extract content from official documentation

## Troubleshooting

### Common Documentation Issues

**Incomplete Information**
- Solution: Use the gap analysis technique to identify missing information
- Action: Interview subject matter experts to fill gaps

**Outdated Content**
- Solution: Establish regular review cycles
- Action: Set calendar reminders for documentation reviews

**Unclear Instructions**
- Solution: Get feedback from new team members
- Action: Have someone follow the instructions exactly as written

**Inconsistent Formatting**
- Solution: Use markdown linting
- Action: Create and enforce a style guide

## Success Metrics

- Documentation completeness (all required topics covered)
- Documentation accuracy (no errors or outdated information)
- User feedback (positive responses from documentation users)
- Reduced support questions (documentation answers common questions)
- Maintenance efficiency (documentation is easy to keep updated)

## Notes

- Documentation is a continuous process, not a one-time task
- Good documentation saves time and improves user experience
- Documentation should evolve with your project
- Invest time in documentation structure to make maintenance easier
- Use templates to ensure consistency and completeness

**Remember**: The goal is to create documentation that helps users accomplish their tasks efficiently and effectively.
