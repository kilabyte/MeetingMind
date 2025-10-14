# Contributing to MeetingMind

Thank you for your interest in contributing to MeetingMind! This document provides guidelines for contributing to the project.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
  - [Reporting Bugs](#reporting-bugs)
  - [Suggesting Features](#suggesting-features)
  - [Contributing Documentation](#contributing-documentation)
  - [Code Contributions](#code-contributions)
- [Issue Guidelines](#issue-guidelines)
- [Pull Request Process](#pull-request-process)
- [Style Guidelines](#style-guidelines)

## Code of Conduct

This project adheres to a Code of Conduct that all contributors are expected to follow. Please be respectful, constructive, and professional in all interactions.

### Our Standards

- Using welcoming and inclusive language
- Being respectful of differing viewpoints and experiences
- Gracefully accepting constructive criticism
- Focusing on what is best for the community
- Showing empathy towards other community members

## How Can I Contribute?

### Reporting Bugs

Bugs are tracked as [GitHub issues](https://github.com/kilabyte/meetingmind/issues). Before creating a bug report, please:

1. **Search existing issues** to avoid duplicates
2. **Check the documentation** to ensure it's not a known limitation
3. **Test with the latest version** to see if the issue still exists

When creating a bug report, include:

- **Clear, descriptive title**
- **Detailed description** of the problem
- **Steps to reproduce** the issue
- **Expected vs actual behavior**
- **Screenshots or recordings** (if applicable)
- **System information**:
  - macOS version (e.g., macOS 15.1 Sequoia)
  - MeetingMind version (found in Settings > About)
  - Meeting platform (Zoom, Teams, Google Meet, Webex)
  - Hardware (Mac model, microphone type)
- **Relevant logs** (if available):
  - Console.app logs filtered for "MeetingMind"
  - Log files from `~/Library/Caches/MeetingMind/logs/` (dev builds)

**Use the [Bug Report Template](https://github.com/kilabyte/meetingmind/issues/new?template=bug_report.md)**

### Suggesting Features

Feature requests are also tracked as [GitHub issues](https://github.com/kilabyte/meetingmind/issues). Before creating a feature request:

1. **Search existing issues** to avoid duplicates
2. **Check the roadmap** to see if it's already planned
3. **Consider the scope** - is it generally useful?

When creating a feature request, include:

- **Clear, descriptive title**
- **Detailed description** of the feature
- **Use case and benefits** - why is this valuable?
- **Proposed solution** (if you have one)
- **Alternative solutions** considered
- **Examples or mockups** (if applicable)
- **Related features** in other apps (for reference)

**Use the [Feature Request Template](https://github.com/kilabyte/meetingmind/issues/new?template=feature_request.md)**

### Contributing Documentation

Documentation improvements are always welcome! You can contribute by:

- **Fixing typos or errors** in existing documentation
- **Improving clarity** of explanations
- **Adding examples** or use cases
- **Creating tutorials** or guides
- **Translating documentation** (future)

Documentation is located in the `docs/` directory:
- `docs/user-guide/` - End-user documentation
- `docs/technical/` - Technical architecture and design
- `docs/troubleshooting/` - Common issues and solutions
- `docs/api/` - API reference and integration guides

### Code Contributions

**Note**: The main codebase is maintained in a private GitLab repository. Direct code contributions to the core application are limited to the development team.

However, you can contribute:

- **Example scripts** for integration with other tools
- **Documentation code samples**
- **Test cases** and reproduction steps
- **Build/deployment scripts** (public components only)

## Issue Guidelines

### Issue Labels

Issues are categorized with labels:

- **bug**: Something isn't working correctly
- **enhancement**: New feature or request
- **documentation**: Documentation improvements
- **question**: Further information is requested
- **duplicate**: This issue or pull request already exists
- **wontfix**: This will not be worked on
- **help-wanted**: Extra attention is needed
- **good-first-issue**: Good for newcomers
- **priority-high**: Critical issues that need immediate attention
- **priority-medium**: Important but not urgent
- **priority-low**: Nice to have

### Issue Lifecycle

1. **Triage**: Team reviews and labels the issue
2. **Discussion**: Community discusses solutions/approaches
3. **Accepted**: Issue approved for work (if applicable)
4. **In Progress**: Work has begun
5. **Review**: Changes are being reviewed
6. **Closed**: Issue is resolved or declined

### Stale Issues

Issues with no activity for 60 days will be marked as stale and may be closed after 14 additional days of inactivity. You can keep an issue open by commenting on it.

## Pull Request Process

**Note**: Pull requests are only accepted for documentation and public tooling.

1. **Fork the repository** and create a branch from `main`
2. **Make your changes** following the style guidelines
3. **Test your changes** thoroughly
4. **Update documentation** as needed
5. **Create a pull request** with:
   - Clear title describing the change
   - Detailed description of what changed and why
   - Link to related issues (e.g., "Fixes #123")
   - Screenshots (if UI changes)

### Pull Request Review

- Pull requests require approval from a maintainer
- Feedback may be provided for revisions
- Once approved, maintainers will merge the PR
- Credit will be given in release notes

## Style Guidelines

### Git Commit Messages

- Use present tense ("Add feature" not "Added feature")
- Use imperative mood ("Move cursor to..." not "Moves cursor to...")
- Limit first line to 72 characters
- Reference issues and pull requests liberally
- Consider starting the commit message with:
  - `docs:` for documentation changes
  - `fix:` for bug fixes
  - `feat:` for new features
  - `chore:` for maintenance tasks

Example:
```
docs: Add troubleshooting guide for USB microphone issues

- Add section on format conversion errors
- Include macOS version compatibility notes
- Add link to system requirements

Fixes #123
```

### Markdown Style

- Use ATX-style headers (`#` not underlines)
- Include blank line before and after headers
- Use fenced code blocks with language identifiers
- Limit line length to 120 characters (soft limit)
- Use relative links for internal references

### Code Style (if applicable)

- Follow Swift API Design Guidelines
- Use meaningful variable and function names
- Add comments for complex logic
- Include docstrings for public APIs

## Questions?

If you have questions about contributing, please:

- Check the [documentation](docs/)
- Search [existing issues](https://github.com/kilabyte/meetingmind/issues)
- Create a new issue with the `question` label
- Contact support via the [website](https://meetingmind.kilabyte.io/support.html)

## Recognition

All contributors will be recognized in:
- Release notes for their contributions
- GitHub contributors list
- Special thanks section (for significant contributions)

Thank you for contributing to MeetingMind! 🎉
