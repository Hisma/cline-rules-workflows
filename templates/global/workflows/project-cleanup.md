# Project Cleanup Workflow

This workflow helps you identify and clean up stale files, outdated documentation, and unnecessary clutter that accumulates as projects evolve.

## Prerequisites
- Working knowledge of the project structure
- Backup or version control of current state
- Time allocated for thorough review (30-60 minutes)

## Steps

1. **Assess Current State**
   - Review project directory structure
   - Identify the project's current phase and active areas
   - Note any recent major changes or refactoring
   - Document what the "clean" state should look like

2. **Identify Stale Files and Directories**
   - Look for empty directories that serve no purpose
   - Find files that haven't been modified in a long time
   - Identify duplicate files or redundant content
   - Check for temporary files that weren't cleaned up

3. **Review Documentation Accuracy**
   - Verify README.md reflects current project state
   - Check that all internal links work correctly
   - Ensure file structure documentation matches reality
   - Update any outdated setup or usage instructions

4. **Clean Up Configuration Files**
   - Remove unused configuration files
   - Clean up commented-out or deprecated settings
   - Verify all configuration files are still needed
   - Update configuration documentation

5. **Organize File Structure**
   - Move misplaced files to appropriate directories
   - Rename files to follow current naming conventions
   - Consolidate related files into logical groupings
   - Remove or archive files that are no longer relevant

6. **Update Dependencies and References**
   - Check for outdated dependency references
   - Update version numbers in documentation
   - Verify all external links still work
   - Remove references to deprecated tools or libraries

7. **Clean Up Development Artifacts**
   - Remove old build artifacts not in .gitignore
   - Clean up temporary test files
   - Remove outdated scripts or tools
   - Clear any cached files that can be regenerated

8. **Verify Project Integrity**
   - Test that the project still builds/runs correctly
   - Verify all documented processes still work
   - Check that cleanup didn't break any functionality
   - Update any affected documentation

9. **Document Changes**
   - Create a summary of what was cleaned up
   - Update CHANGELOG if applicable
   - Note any structural changes made
   - Document new organization patterns for future reference

## Success Criteria
- Project directory structure is logical and current
- All documentation accurately reflects project state
- No stale or unnecessary files remain
- All links and references work correctly
- Project builds and runs without issues
- Team members can easily navigate and understand the structure

## Common Cleanup Patterns

### Documentation Projects
- Remove outdated content files
- Clean up unused image assets
- Update navigation and cross-references
- Verify all examples still work

### Code Projects
- Remove unused source files
- Clean up old test files
- Update build configurations
- Remove deprecated dependencies

### Configuration Projects
- Remove unused configuration files
- Clean up old environment settings
- Update documentation for current configs
- Remove obsolete scripts

## Cleanup Checklist

### Files and Directories
- [ ] Empty directories removed
- [ ] Duplicate files consolidated
- [ ] Temporary files cleaned up
- [ ] Misplaced files moved to correct locations
- [ ] Unused files removed or archived

### Documentation
- [ ] README.md updated and accurate
- [ ] Internal links verified and working
- [ ] File structure documentation current
- [ ] Setup instructions tested and updated
- [ ] Examples verified to work

### Configuration
- [ ] Unused config files removed
- [ ] Deprecated settings cleaned up
- [ ] Configuration documentation updated
- [ ] Environment setup verified

### Dependencies and References
- [ ] External links verified
- [ ] Version numbers updated
- [ ] Deprecated references removed
- [ ] Dependency documentation current

## Troubleshooting

### Unsure if File is Needed
- Check git history to see when it was last modified
- Search codebase for references to the file
- Ask team members if they recognize its purpose
- Move to archive folder rather than deleting immediately

### Breaking Changes During Cleanup
- Use version control to revert problematic changes
- Test incrementally rather than making all changes at once
- Keep detailed notes of what was changed
- Have a rollback plan before starting major cleanup

### Large Amount of Cleanup Needed
- Break cleanup into phases (documentation, code, config)
- Focus on highest-impact areas first
- Schedule multiple cleanup sessions
- Consider automating repetitive cleanup tasks

## Automation Opportunities

### Scripts for Common Tasks
- Find and list empty directories
- Identify files not modified in X days
- Check for broken internal links
- Validate configuration file syntax

### Regular Maintenance
- Schedule monthly cleanup reviews
- Set up automated checks for common issues
- Create alerts for accumulating temporary files
- Implement pre-commit hooks for file organization

## Best Practices

### Prevention
- Establish clear file organization standards
- Use .gitignore effectively to prevent clutter
- Regular small cleanups rather than large overhauls
- Document file organization decisions

### Execution
- Make incremental changes and test frequently
- Keep detailed notes of what was changed
- Involve team members in cleanup decisions
- Use version control to track cleanup changes

### Maintenance
- Schedule regular cleanup sessions
- Update cleanup criteria as project evolves
- Share cleanup learnings with team
- Continuously improve cleanup processes

Remember: The goal is to maintain a clean, navigable project structure that supports productive development. Regular cleanup prevents technical debt from accumulating and makes the project more maintainable for everyone.
