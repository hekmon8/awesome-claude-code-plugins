# Contributing to Awesome Claude Code Plugins

Thank you for your interest in contributing! This document provides guidelines for contributing to this collection.

## Table of Contents

- [How to Contribute](#how-to-contribute)
- [Adding a Plugin](#adding-a-plugin)
- [Adding a Marketplace](#adding-a-marketplace)
- [Improving Documentation](#improving-documentation)
- [Reporting Issues](#reporting-issues)
- [Submission Guidelines](#submission-guidelines)
- [Quality Standards](#quality-standards)

## How to Contribute

There are several ways to contribute:

1. **Add Your Plugin**: Share plugins you've created
2. **Add Marketplaces**: List plugin marketplaces you know about
3. **Improve Documentation**: Enhance guides and examples
4. **Report Issues**: Help us find broken links or outdated information
5. **Share Tutorials**: Write guides and tutorials
6. **Suggest Improvements**: Propose new categories or organization

## Adding a Plugin

### Requirements

Before adding a plugin, ensure it meets these criteria:

- ✅ **Works with Claude Code**: Plugin is functional and tested
- ✅ **Well-Documented**: Includes README with clear instructions
- ✅ **Open Source** (preferred): Code is publicly available
- ✅ **Maintained**: Active development or stable release
- ✅ **Quality**: Provides real value to Claude Code users
- ✅ **Safe**: No malicious code or security risks

### Submission Process

1. **Fork this repository**

2. **Add your plugin to the `plugins/` directory**:

```bash
git clone https://github.com/hekmon8/awesome-claude-code-plugins
cd awesome-claude-code-plugins
git checkout -b add-my-plugin
```

3. **Create your plugin directory**:

```
plugins/
├── your-plugin-name/
│   ├── commands/          # Slash commands (if any)
│   ├── agents/            # AI agents (if any)
│   ├── .claude-plugin/
│   │   └── plugin.json    # Plugin configuration
│   └── README.md          # Plugin documentation
```

4. **Update `.claude-plugin/marketplace.json`**:

Add your plugin entry to the `plugins` array:

```json
{
  "name": "your-plugin-name",
  "source": "./plugins/your-plugin-name",
  "description": "Brief description of your plugin",
  "version": "1.0.0",
  "author": {
    "name": "Your Name",
    "email": "your-email@example.com"
  },
  "license": "MIT",
  "keywords": ["keyword1", "keyword2"],
  "strict": false,
  "metadata": {
    "category": "Development Tools",
    "featured": false,
    "type": "plugin"
  }
}
```

5. **Add your plugin to `README.md`**:

Add an entry in the appropriate category:

```markdown
### Your Category

- **your-plugin-name** - Brief description
  - Location: `plugins/your-plugin-name`
  - Features: Key capabilities
  - Author: Your Name
```

6. **Follow the format**:
```markdown
- **plugin-name** - Concise description (max 100 chars)
  - Location: `plugins/plugin-name`
  - Features: Key capabilities
  - Author: Author Name
```

7. **Place in correct category**:
   - Development Tools
   - DevOps & CI/CD
   - Testing & Quality
   - Documentation
   - Project Management
   - Security
   - (or suggest a new category)

8. **Submit a Pull Request** with:
   - Clear title: "Add [plugin-name] plugin"
   - Description of what the plugin does
   - Confirmation that you've tested it
   - Confirmation that you've updated both `marketplace.json` and `README.md`

### Example Entry

#### In `.claude-plugin/marketplace.json`:
```json
{
  "name": "feature-planner",
  "source": "./plugins/feature-planner",
  "description": "Interactive feature planning with task breakdown",
  "version": "1.0.0",
  "author": {
    "name": "Acme Corp",
    "email": "contact@acmecorp.com"
  },
  "license": "MIT",
  "keywords": ["planning", "features", "tasks"],
  "strict": false,
  "metadata": {
    "category": "Development Tools",
    "featured": false,
    "type": "plugin"
  }
}
```

#### In `README.md`:
```markdown
### Development Tools

- **feature-planner** - Interactive feature planning with task breakdown
  - Location: `plugins/feature-planner`
  - Features: User story analysis, task generation, estimation
  - Author: Acme Corp
```

## Note on Plugin Marketplaces

**This repository collects individual plugins, not plugin marketplaces.**

If you have created a plugin marketplace (a repository containing multiple plugins), you should:

1. **Submit individual plugins** from your marketplace following the plugin submission process above
2. **Reference your marketplace** in each plugin's README for context
3. **Include a link** to your marketplace repository in the plugin description

We focus on cataloging individual plugins to make it easier for users to discover and evaluate specific tools. Plugin marketplace repositories are welcome to list their plugins here individually.

## Improving Documentation

Documentation improvements are always welcome!

### Areas to Improve

- **Tutorials**: Write step-by-step guides
- **Examples**: Add more plugin examples
- **Architecture Docs**: Improve technical documentation
- **Best Practices**: Share tips and patterns
- **Troubleshooting**: Add solutions to common problems

### Documentation Standards

- **Clear and Concise**: Easy to understand
- **Well-Structured**: Use headings and lists
- **Code Examples**: Include practical examples
- **Up-to-Date**: Verify accuracy with current Claude Code version
- **Markdown Format**: Follow markdown best practices

## Reporting Issues

Found a problem? Please open an issue with:

- **Clear Title**: Describe the issue briefly
- **Description**: Detailed explanation
- **Steps to Reproduce**: If applicable
- **Expected vs Actual**: What should happen vs what does happen
- **Environment**: Claude Code version, OS, etc.

### Issue Categories

- 🐛 **Bug**: Something isn't working
- 📝 **Documentation**: Improve or update docs
- 💡 **Enhancement**: Suggest improvements
- ❓ **Question**: Ask for help or clarification
- 🔗 **Broken Link**: Report dead links
- 🔄 **Update Needed**: Outdated information

## Submission Guidelines

### Pull Request Process

1. **Fork and Branch**:
```bash
# First, fork the repository on GitHub
# Then clone your fork
git clone https://github.com/your-username/awesome-claude-code-plugins
cd awesome-claude-code-plugins
git checkout -b add-my-plugin
```

2. **Make Changes**:
   - Add plugin files to `plugins/your-plugin-name/` directory
   - Update `.claude-plugin/marketplace.json` with plugin entry
   - Add plugin entry to `README.md` in appropriate category
   - Follow existing formatting
   - Test all links
   - Check spelling and grammar
   - Ensure alphabetical ordering within categories

3. **Commit**:
```bash
git add .
git commit -m "Add [plugin-name] to [category]"
```

4. **Push and Create PR**:
```bash
git push origin add-my-plugin
```
   - Go to GitHub and create Pull Request
   - Fill out PR template
   - Link related issues (if any)

### PR Review Criteria

Your PR will be reviewed for:

- ✅ **Accuracy**: Information is correct
- ✅ **Formatting**: Follows existing style
- ✅ **Completeness**: All required information included
- ✅ **Quality**: Plugin/resource meets quality standards
- ✅ **Relevance**: Appropriate for this collection
- ✅ **Links**: All links work correctly

### Response Time

- We aim to review PRs within **7 days**
- Complex submissions may take longer
- You may be asked for clarifications or changes

## Quality Standards

### Plugin Quality

Plugins in this list should:

- **Work Reliably**: No critical bugs
- **Be Documented**: Clear README and usage instructions
- **Add Value**: Solve real problems for users
- **Be Maintained**: Active or stable
- **Be Safe**: No security vulnerabilities or malicious code

### Documentation Quality

Documentation should:

- **Be Accurate**: Technically correct
- **Be Clear**: Easy to understand
- **Be Complete**: Cover all necessary information
- **Be Current**: Up-to-date with latest Claude Code
- **Include Examples**: Practical code samples

### Code of Conduct

- **Be Respectful**: Treat all contributors with respect
- **Be Constructive**: Provide helpful feedback
- **Be Inclusive**: Welcome diverse perspectives
- **Be Professional**: Maintain professional communication
- **Give Credit**: Acknowledge others' work

## Style Guide

### Markdown Formatting

```markdown
# Main Heading (H1)

## Section (H2)

### Subsection (H3)

**Bold** for emphasis
*Italic* for terms
`code` for inline code
```

### Lists

```markdown
- Unordered list item
  - Nested item
  - Another nested item

1. Ordered list item
2. Second item
```

### Links

```markdown
[Link Text](https://example.com)
[Relative Link](./docs/guide.md)
```

### Code Blocks

````markdown
```bash
# Bash command
claude --version
```

```json
{
  "name": "example"
}
```
````

## Recognition

Contributors will be recognized in:

- **README.md**: Contributors section
- **GitHub**: Contributor graph
- **Release Notes**: Major contributions highlighted

## Getting Help

Need help contributing?

- 💬 [Discord Community](https://anthropic.com/discord)
- 💬 [Claude Code Issues](https://github.com/anthropics/claude-code/issues)
- 📧 Create an issue with the "question" label

## Additional Resources

- [Claude Code Documentation](https://docs.anthropic.com/en/docs/claude-code/overview)
- [Creating Plugins Guide](https://docs.anthropic.com/en/docs/claude-code/plugins)
- [Markdown Guide](https://www.markdownguide.org/)
- [Awesome List Guidelines](https://github.com/sindresorhus/awesome/blob/main/contributing.md)

## License

By contributing, you agree that your contributions will be licensed under the same license as this project (CC0 1.0 Universal).

---

**Thank you for contributing to make this resource better for everyone!** 🎉
