# Contributing to GenAI Coach

Thank you for your interest in contributing to GenAI Coach! We're building an open, people-first AI education platform and welcome contributions from the community.

## Overview

GenAI Coach aims to provide foundational AI education with ethical principles at its core. We value contributions that advance accessible, responsible AI learning for everyone.

## Prerequisites

Before contributing, ensure you have:

- **Git LFS**: Required for handling large AI/ML files
- **Ruby 3.2.3+**: For Jekyll development
- **Bundler**: For managing Ruby dependencies

For detailed setup instructions, see [Local Development Guide](./docs/local-development.md).

## Local Development

### Quick Setup

1. **Clone and setup:**
   ```bash
   git clone https://github.com/genai-coach/ai.git
   cd ai
   git lfs install && git lfs pull
   ```

2. **Install dependencies:**
   ```bash
   sudo bundle install
   ```

3. **Run locally:**
   ```bash
   bundle exec jekyll serve --host 0.0.0.0 --port 4000
   # Visit: http://localhost:4000/ai/
   ```

For comprehensive setup guidance, see the [Local Development Guide](./docs/local-development.md).

## Branching & Commit Conventions

### Branching Strategy

- **`main`**: Production-ready code
- **Feature branches**: `feature/descriptive-name`
- **Documentation**: `docs/descriptive-name`
- **Fixes**: `fix/descriptive-name`

### Commit Messages

We use [Conventional Commits](https://www.conventionalcommits.org/):

```
<type>: <description>

[optional body]
```

**Types:**
- `feat`: New features
- `fix`: Bug fixes
- `docs`: Documentation changes
- `style`: Formatting, missing semicolons, etc.
- `refactor`: Code restructuring
- `test`: Adding/updating tests
- `chore`: Maintenance tasks

**Examples:**
- `docs: add architecture overview`
- `feat: implement course navigation`
- `fix: resolve LFS file tracking issue`

## Opening Pull Requests

### Guidelines

- **Keep PRs small and focused** on a single purpose
- **Write clear descriptions** explaining what and why
- **Reference related issues** using `Fixes #123` or `Addresses #123`
- **Test locally** before submitting

### PR Template

Include:
1. **Purpose**: What does this PR accomplish?
2. **Changes**: List key modifications
3. **Testing**: How was this tested?
4. **Screenshots**: For UI changes

## Review Guidelines

### For Contributors

- **Be responsive** to feedback
- **Keep discussions respectful** and constructive
- **Update PRs promptly** when requested

### For Reviewers

- **Focus on code quality** and documentation clarity
- **Provide specific, actionable feedback**
- **Consider the educational mission** in your reviews
- **Be encouraging** to new contributors

## Issue Reporting

### Before Creating an Issue

1. **Search existing issues** for duplicates
2. **Check documentation** for known solutions
3. **Test with latest version** when possible

### Issue Types

- **Bug Reports**: Unexpected behavior or errors
- **Feature Requests**: New functionality suggestions
- **Documentation**: Improvements to guides or clarity
- **Questions**: Usage help or clarification

### Writing Good Issues

- **Use descriptive titles**
- **Provide clear steps to reproduce** (for bugs)
- **Include environment details** (OS, Ruby version, etc.)
- **Add screenshots** when helpful

## Future Documentation Roadmap

We're actively expanding our documentation:

- **Advanced Architecture**: Detailed system design and data flow
- **Course Development Guide**: Creating educational content
- **Accessibility Guidelines**: Ensuring inclusive design
- **API Documentation**: For future integrations
- **Deployment Guide**: Production deployment strategies
- **Community Guidelines**: Detailed interaction standards

## Code of Conduct

This project follows the [Contributor Covenant Code of Conduct](./CODE_OF_CONDUCT.md). By participating, you agree to uphold this code.

## Questions?

- **General questions**: Open a GitHub Discussion
- **Bugs**: Create an issue with the bug template
- **Security concerns**: Follow our Security Policy (coming soon)

We appreciate your contributions to making AI education more accessible and ethical!