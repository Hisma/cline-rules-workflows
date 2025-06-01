# Coding Standards Workflow

## Overview

This workflow guides you through applying and enforcing coding standards across your projects. It helps ensure code consistency, maintainability, and quality.

## When to Use

- When starting a new project
- When onboarding new team members
- During code reviews
- When refactoring existing code
- Before submitting pull requests

## Prerequisites

- Project codebase
- Appropriate linting tools for your languages
- Code editor with linting support
- Version control system (Git)

## General Principles

### Code Quality

- Write clean, readable, and maintainable code
- Use meaningful variable and function names
- Keep functions small and focused on a single responsibility
- Avoid deep nesting - prefer early returns and guard clauses
- Write self-documenting code that explains the "why" not just the "what"

### Naming Conventions

- Use descriptive names that clearly indicate purpose
- Prefer longer, clear names over short, cryptic ones
- Use consistent naming patterns within the same codebase
- Follow language-specific conventions (camelCase, snake_case, etc.)

### Code Organization

- Group related functionality together
- Separate concerns into different modules/files
- Use consistent file and folder structure
- Keep configuration separate from business logic

### Error Handling

- Handle errors gracefully and provide meaningful messages
- Use appropriate error handling patterns for the language
- Log errors with sufficient context for debugging
- Fail fast when appropriate, but recover gracefully when possible

## Language-Specific Guidelines

### JavaScript/TypeScript

- Use TypeScript when possible for better type safety
- Prefer `const` and `let` over `var`
- Use arrow functions for short, simple functions
- Destructure objects and arrays when it improves readability
- Use template literals for string interpolation

### Python

- Follow PEP 8 style guidelines
- Use type hints for function parameters and return values
- Prefer list comprehensions for simple transformations
- Use context managers (`with` statements) for resource management
- Write docstrings for all public functions and classes

### General Web Development

- Use semantic HTML elements
- Write accessible markup with proper ARIA labels
- Optimize for performance (lazy loading, code splitting, etc.)
- Follow responsive design principles
- Validate user input on both client and server side

## Workflow Steps

### Step 1: Set Up Linting Tools

#### For JavaScript/TypeScript Projects:

```bash
# Install ESLint and Prettier
npm install --save-dev eslint prettier eslint-config-prettier eslint-plugin-prettier

# Create ESLint configuration
cat > .eslintrc.json << 'EOF'
{
  "extends": ["eslint:recommended", "prettier"],
  "plugins": ["prettier"],
  "rules": {
    "prettier/prettier": "error"
  },
  "parserOptions": {
    "ecmaVersion": "latest",
    "sourceType": "module"
  }
}
EOF

# Create Prettier configuration
cat > .prettierrc << 'EOF'
{
  "singleQuote": true,
  "trailingComma": "es5",
  "printWidth": 100,
  "tabWidth": 2,
  "semi": true
}
EOF
```

#### For Python Projects:

```bash
# Install linting tools
pip install black flake8 mypy isort

# Create configuration files
cat > pyproject.toml << 'EOF'
[tool.black]
line-length = 88
target-version = ['py38']

[tool.isort]
profile = "black"
line_length = 88
EOF

cat > .flake8 << 'EOF'
[flake8]
max-line-length = 88
extend-ignore = E203
EOF
```

### Step 2: Configure Editor Integration

#### VS Code Setup:

```json
// settings.json
{
  "editor.formatOnSave": true,
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
  },
  "python.linting.enabled": true,
  "python.linting.flake8Enabled": true,
  "python.formatting.provider": "black",
  "editor.defaultFormatter": "esbenp.prettier-vscode"
}
```

#### JetBrains IDEs:

- Enable ESLint/Prettier in Settings > Languages & Frameworks
- Enable Black/Flake8 in Settings > Tools > Python Integrated Tools

### Step 3: Create Pre-commit Hooks

```bash
# Install pre-commit
pip install pre-commit

# Create pre-commit configuration
cat > .pre-commit-config.yaml << 'EOF'
repos:
  - repo: https://github.com/pre-commit/pre-commit-hooks
    rev: v4.4.0
    hooks:
      - id: trailing-whitespace
      - id: end-of-file-fixer
      - id: check-yaml
      - id: check-json

  # JavaScript/TypeScript
  - repo: https://github.com/pre-commit/mirrors-eslint
    rev: v8.38.0
    hooks:
      - id: eslint
        files: \.(js|ts|jsx|tsx)$
        additional_dependencies:
          - eslint@8.38.0
          - eslint-config-prettier@8.8.0
          - eslint-plugin-prettier@4.2.1
          - prettier@2.8.7

  # Python
  - repo: https://github.com/psf/black
    rev: 23.3.0
    hooks:
      - id: black
  
  - repo: https://github.com/pycqa/flake8
    rev: 6.0.0
    hooks:
      - id: flake8
  
  - repo: https://github.com/pycqa/isort
    rev: 5.12.0
    hooks:
      - id: isort
EOF

# Install the pre-commit hooks
pre-commit install
```

### Step 4: Run Initial Linting

```bash
# JavaScript/TypeScript
npx eslint --fix "**/*.{js,ts,jsx,tsx}"
npx prettier --write "**/*.{js,ts,jsx,tsx,json,css,md}"

# Python
black .
flake8 .
isort .
```

### Step 5: Set Up CI/CD Linting Checks

#### GitHub Actions Example:

```yaml
# .github/workflows/lint.yml
name: Lint

on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]

jobs:
  lint:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v3
    
    - name: Set up Node.js
      uses: actions/setup-node@v3
      with:
        node-version: '18'
    
    - name: Install JS dependencies
      run: npm ci
    
    - name: Lint JavaScript
      run: npx eslint "**/*.{js,ts,jsx,tsx}"
    
    - name: Set up Python
      uses: actions/setup-python@v4
      with:
        python-version: '3.10'
    
    - name: Install Python dependencies
      run: |
        python -m pip install --upgrade pip
        pip install black flake8 isort
    
    - name: Lint Python
      run: |
        black --check .
        flake8 .
        isort --check .
```

### Step 6: Document Coding Standards

Create a `CODING_STANDARDS.md` file in your repository:

```markdown
# Project Coding Standards

This document outlines the coding standards for this project.

## General Guidelines

- Write clean, readable, and maintainable code
- Use meaningful variable and function names
- Keep functions small and focused
- Document complex logic and business rules
- Write tests for all new features

## JavaScript/TypeScript Standards

- Use TypeScript for type safety
- Follow ESLint and Prettier configurations
- Use async/await for asynchronous code
- Document public APIs with JSDoc comments
- Use functional programming patterns when appropriate

## Python Standards

- Follow PEP 8 style guidelines
- Use type hints
- Write docstrings for all public functions and classes
- Use virtual environments for dependency management
- Follow the Zen of Python

## Code Review Checklist

- [ ] Code follows project standards
- [ ] Tests are included and pass
- [ ] Documentation is updated
- [ ] No unnecessary complexity
- [ ] Error handling is appropriate
- [ ] Security considerations addressed
```

### Step 7: Code Review Process

1. **Before Submitting Code for Review**:
   - Run linters and formatters
   - Fix all linting errors
   - Ensure tests pass
   - Self-review your code

2. **During Code Review**:
   - Check adherence to coding standards
   - Verify functionality and correctness
   - Look for security issues
   - Suggest improvements for readability and maintainability

3. **After Code Review**:
   - Address all feedback
   - Re-run linters and tests
   - Request another review if significant changes were made

## Best Practices

### Maintaining Standards Over Time

- Regularly update linting rules as project evolves
- Conduct periodic code quality reviews
- Refactor legacy code to meet current standards
- Train new team members on coding standards
- Automate as much as possible

### Handling Legacy Code

- Apply standards to new code first
- Gradually refactor legacy code
- Use "boy scout rule" - leave code better than you found it
- Document technical debt and plan for addressing it
- Consider using tools like SonarQube for technical debt tracking

### Balancing Standards with Productivity

- Focus on standards that provide the most value
- Automate formatting and simple rules
- Be pragmatic - know when to make exceptions
- Get team buy-in on standards
- Regularly review and adjust standards based on team feedback

## Troubleshooting

### Common Issues

- **Linter conflicts**: Ensure consistent configuration across tools
- **CI/CD failures**: Test linting locally before pushing
- **Team resistance**: Explain benefits and get buy-in
- **Performance issues**: Optimize linting for large codebases
- **False positives**: Adjust rules or add specific exceptions

### Resolving Conflicts

```bash
# Check for conflicting rules
npx eslint-config-prettier .eslintrc.json

# Disable specific rules in specific files
// eslint-disable-next-line rule-name
```

## Success Criteria

- All new code follows established standards
- Linting is integrated into development workflow
- CI/CD enforces standards automatically
- Code reviews include standards verification
- Team members understand and follow standards
- Codebase becomes more consistent over time

## Notes

- Coding standards should evolve with the project
- Balance strictness with practicality
- Focus on standards that improve code quality
- Automate as much as possible to reduce friction
- Get team buy-in for better adherence

**Remember**: The goal of coding standards is to improve code quality and team efficiency, not to create bureaucracy or slow down development.
