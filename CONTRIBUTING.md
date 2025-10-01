# Contributing to Business Process Catalog (BPC)

Thank you for your interest in contributing to the BPC template! This document provides guidelines for contributing.

## How to Contribute

We welcome contributions in several forms:

### 1. Report Issues

If you encounter problems or have suggestions:

- Check if the issue already exists in [GitHub Issues](https://github.com/MVPJuanBravo/BPC/issues)
- If not, create a new issue with:
  - Clear title describing the problem
  - Detailed description of the issue
  - Steps to reproduce (if applicable)
  - Expected vs actual behavior
  - Your environment (Azure DevOps version, Process Migrator version)

### 2. Suggest Enhancements

Have ideas for improving the template?

- Open an issue with the "enhancement" label
- Describe the feature and its benefits
- Provide examples of how it would be used
- Consider implementation complexity

### 3. Submit Pull Requests

Want to contribute code or documentation?

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/your-feature-name`
3. Make your changes
4. Test your changes thoroughly
5. Commit with clear messages: `git commit -m "Add: description of changes"`
6. Push to your fork: `git push origin feature/your-feature-name`
7. Open a Pull Request with:
   - Clear description of changes
   - Reference to related issues
   - Screenshots (if applicable)

## Contribution Areas

### Documentation

- Improve README or other documentation
- Add tutorials or guides
- Create video walkthroughs
- Translate documentation to other languages

### Template Enhancements

- Add new custom fields
- Create new work item types
- Improve workflow states
- Add automation rules

### Examples

- Share industry-specific customizations
- Provide sample processes
- Create integration examples
- Document best practices

### Testing

- Test the template in different scenarios
- Report compatibility issues
- Validate Process Migrator integration
- Test on different Azure DevOps versions

## Coding Standards

### JSON Files

- Use consistent indentation (2 spaces)
- Validate JSON syntax before committing
- Include comments where helpful (if format supports)
- Follow naming conventions

### Markdown Documentation

- Use clear headings and structure
- Include code examples with syntax highlighting
- Add links to related resources
- Keep line length reasonable (80-100 characters when possible)

### Naming Conventions

- **Fields**: Use PascalCase (e.g., ProcessOwner)
- **Work Item Types**: Use proper case with spaces (e.g., Business Process)
- **Files**: Use kebab-case (e.g., quick-start.md)

## Testing Your Changes

Before submitting:

1. **Validate JSON**: Ensure all JSON files are valid
2. **Test Import**: Try importing the template using Process Migrator
3. **Check Documentation**: Verify all links and references work
4. **Review Changes**: Use `git diff` to review what you've changed
5. **Test Instructions**: Follow your own documentation to ensure it works

## Pull Request Process

1. **Update Documentation**: If you change functionality, update the README
2. **Add Examples**: Include examples of your changes where helpful
3. **Reference Issues**: Link to related issues in your PR description
4. **Request Review**: Tag maintainers for review
5. **Address Feedback**: Respond to review comments promptly
6. **Keep PR Focused**: One feature or fix per PR

## Commit Message Guidelines

Use clear, descriptive commit messages:

```
Add: New feature or file
Update: Changes to existing functionality
Fix: Bug fixes
Docs: Documentation changes
Refactor: Code restructuring without functionality changes
Test: Adding or updating tests
```

Example:
```
Add: Custom field for process automation level
Update: README with new installation steps
Fix: JSON syntax error in configuration.json
Docs: Add troubleshooting section to QUICKSTART.md
```

## Community Guidelines

### Be Respectful

- Be welcoming to newcomers
- Respect different viewpoints
- Accept constructive criticism
- Focus on what's best for the community

### Be Clear

- Provide context in discussions
- Use clear, understandable language
- Ask for clarification when needed
- Share knowledge generously

### Be Collaborative

- Work together to find solutions
- Share credit for contributions
- Help review others' contributions
- Celebrate successes together

## Recognition

Contributors will be:
- Listed in the repository contributors page
- Mentioned in release notes for significant contributions
- Credited in documentation where appropriate

## Questions?

If you have questions about contributing:
- Open a discussion in GitHub Discussions
- Reach out to the maintainers
- Check existing issues and PRs for similar questions

## License

By contributing, you agree that your contributions will be licensed under the same terms as the project.

---

Thank you for helping make BPC better for everyone! 🎉
