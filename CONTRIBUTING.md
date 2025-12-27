# Contributing to QA Foundations

Thank you for considering contributing to QA Foundations. This document provides guidelines and instructions for contributing.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
- [Getting Started](#getting-started)
- [Pull Request Process](#pull-request-process)
- [Style Guidelines](#style-guidelines)
- [Community](#community)

---

## Code of Conduct

This project and everyone participating in it is governed by our [Code of Conduct](CODE_OF_CONDUCT.md). By participating, you are expected to uphold this code.

---

## How Can I Contribute?

### Documentation Improvements

- Fix typos or grammatical errors
- Add more examples to existing documents
- Improve explanations or diagrams
- Translate content to other languages

### Add Test Cases

- Add test cases for new modules/features
- Improve existing test cases with edge cases
- Add test data examples

### Bug Report Examples

- Add real-world bug report examples
- Include different severity/priority scenarios
- Add bug reports from different domains

### New Documentation

- Add new QA concepts or methodologies
- Create tutorials for QA tools
- Add interview preparation content

### Suggest Enhancements

Have ideas for new content? Open an issue to discuss.

---

## Getting Started

### Prerequisites

- Git installed on your machine
- GitHub account
- Basic understanding of Markdown

### Fork and Clone

1. **Fork the repository**
   - Click the "Fork" button on GitHub

2. **Clone your fork**
   ```bash
   git clone https://github.com/YOUR-USERNAME/qa-foundations.git
   cd qa-foundations
   ```

3. **Add upstream remote**
   ```bash
   git remote add upstream https://github.com/YasinAsif/qa-foundations.git
   ```

4. **Create a branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```

---

## Pull Request Process

### Before Submitting

1. Ensure your content follows the style guidelines
2. Check for spelling and grammar errors
3. Update the README if adding new files
4. Test any links you've added

### Submitting a PR

1. **Commit your changes**
   ```bash
   git add .
   git commit -m "Add: brief description of your changes"
   ```

2. **Push to your fork**
   ```bash
   git push origin feature/your-feature-name
   ```

3. **Create Pull Request**
   - Go to your fork on GitHub
   - Click "New Pull Request"
   - Fill in the PR template
   - Submit for review

### PR Review

- PRs require at least 1 approval before merging
- Address any feedback from reviewers
- Keep your PR focused on a single topic

---

## Style Guidelines

### Markdown Formatting

```markdown
# H1 - Document Title (use once per file)
## H2 - Major Sections
### H3 - Subsections

**Bold** for emphasis
`code` for technical terms
```

### File Naming

- Use lowercase with hyphens: `test-cases-login.md`
- Be descriptive: `api-testing-guide.md` not `doc1.md`

### Documentation Structure

```markdown
# Title

## Overview
Brief description of the topic

## Content
Main content with examples

## Summary
Key takeaways

## Resources (optional)
Additional learning materials
```

### Test Case Format

| Field | Description |
|-------|-------------|
| TC ID | Unique identifier (TC_MODULE_001) |
| Title | Brief description |
| Priority | High/Medium/Low |
| Steps | Numbered steps |
| Expected Result | Clear outcome |

### Bug Report Format

| Field | Required |
|-------|----------|
| Summary | Yes |
| Severity | Yes |
| Steps to Reproduce | Yes |
| Expected Result | Yes |
| Actual Result | Yes |
| Screenshots | Optional |

---

## Commit Message Guidelines

Use semantic commit messages:

| Type | Description |
|------|-------------|
| `Add:` | New content or files |
| `Update:` | Changes to existing content |
| `Fix:` | Corrections (typos, errors) |
| `Remove:` | Deleted content |
| `Refactor:` | Restructuring without content change |

**Examples:**
```
Add: performance testing documentation
Update: login test cases with edge cases
Fix: typo in STLC diagram
Remove: outdated references
```

---

## Recognition

Contributors will be:
- Listed in our Contributors section
- Credited in release notes
- Part of the QA Foundations community

---

## Community

- **Questions?** Open a [Discussion](https://github.com/YasinAsif/qa-foundations/discussions)
- **Issues?** Check [existing issues](https://github.com/YasinAsif/qa-foundations/issues) first
- **Ideas?** We welcome your suggestions

---

## License

By contributing, you agree that your contributions will be shared under the same license as this project.

---

Thank you for contributing.
