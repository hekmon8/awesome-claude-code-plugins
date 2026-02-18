# Awesome Claude Code Plugins [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of awesome Claude Code plugins, marketplaces, tools, and resources.

[Claude Code](https://docs.anthropic.com/en/docs/claude-code/overview) is an agentic coding tool that lives in your terminal and IDE. With the plugin system (released October 2025), you can now extend Claude Code with custom slash commands, specialized agents, MCP servers, and workflow hooks.

## Contents

- [Official Resources](#official-resources)
- [What are Claude Code Plugins?](#what-are-claude-code-plugins)
- [Getting Started](#getting-started)
- [Plugin Marketplaces](#plugin-marketplaces)
- [Featured Plugins](#featured-plugins)
  - [Development Tools](#development-tools)
  - [DevOps & CI/CD](#devops--cicd)
  - [Testing & Quality](#testing--quality)
  - [Documentation](#documentation)
  - [Project Management](#project-management)
  - [Security](#security)
- [Creating Plugins](#creating-plugins)
- [Examples](#examples)
- [Tutorials](#tutorials)
- [Community](#community)
- [Contributing](#contributing)

## Official Resources

- [Claude Code Documentation](https://docs.anthropic.com/en/docs/claude-code/overview) - Official documentation
- [Plugin System Announcement](https://www.anthropic.com/news/claude-code-plugins) - Official plugin launch blog post
- [Plugin Reference](https://docs.anthropic.com/en/docs/claude-code/plugins-reference) - Technical plugin specification
- [Creating Plugins Guide](https://docs.anthropic.com/en/docs/claude-code/plugins) - Official plugin creation guide
- [Plugin Marketplaces Guide](https://docs.anthropic.com/en/docs/claude-code/plugin-marketplaces) - How to publish plugins
- [Anthropic's Official Plugins](https://github.com/anthropics/claude-code) - Example plugins by Anthropic

## What are Claude Code Plugins?

Claude Code plugins are custom collections that can include:

- **🔧 Slash Commands**: Custom shortcuts for frequently-used operations
- **🤖 Subagents**: Specialized agents for specific development tasks
- **🔌 MCP Servers**: Connections to tools and data sources via Model Context Protocol
- **🪝 Hooks**: Automated actions triggered at key workflow points

### Key Benefits

- **📦 One-Command Installation**: Install complete workflows with `/plugin install`
- **🎛️ Toggle On/Off**: Enable plugins when needed, disable to reduce context
- **🔄 Version Management**: Track and update plugin versions automatically
- **🌐 Share & Collaborate**: Distribute plugins via marketplaces
- **⚙️ Standardization**: Enforce team standards and best practices

## Getting Started

### Prerequisites

- Claude Code installed (`npm install -g @anthropic-ai/claude-code`)
- Claude API key configured
- Git (for marketplace installations)

### Quick Start

1. **Add this marketplace**:
```bash
/plugin marketplace add hekmon8/awesome-claude-code-plugins
```

2. **Or add other marketplaces**:
```bash
/plugin marketplace add anthropics/claude-code
/plugin marketplace add davila7/claude-code-templates
```

3. **Browse available plugins**:
```bash
/plugin
```

4. **Install a plugin**:
```bash
/plugin install feature-dev
```

5. **Use the plugin**:
```bash
# Plugin commands are now available
/feature-spec "Add user authentication"
```

### Installation Methods

```bash
# From this awesome collection
/plugin marketplace add hekmon8/awesome-claude-code-plugins

# From other GitHub marketplaces
/plugin marketplace add owner/repo

# From Git repository
/plugin marketplace add https://gitlab.com/company/plugins.git

# From local directory (for development)
/plugin marketplace add ./my-plugins
```

## Plugin Marketplaces

### Official & Community Marketplaces

- **[Anthropic Official Plugins](https://github.com/anthropics/claude-code)** - `anthropics/claude-code`
  - Feature development workflows
  - PR review automation
  - Security guidance
  - Plugin creation meta-plugin

- **[Dan Ávila's Plugin Marketplace](https://www.aitmpl.com/plugins)** - DevOps, docs, testing
  - DevOps automation plugins
  - Documentation generation
  - Project management tools
  - Testing suites

- **[Seth Hobson's Agents Collection](https://github.com/wshobson/agents)** - `wshobson/agents`
  - 80+ specialized sub-agents
  - Domain-specific development agents
  - Workflow automation

## Featured Plugins

### Development Tools

- **feature-dev** (Anthropic) - Complete feature development workflow
- **code-review** (Anthropic) - Automated code review with best practices
- **refactor-assistant** - Safe refactoring with automated testing

### DevOps & CI/CD

- **deploy-automation** - Deployment pipeline management
- **docker-helper** - Container workflow automation
- **k8s-deploy** - Kubernetes deployment assistance

### Testing & Quality

- **test-generator** - Automated test case generation
- **coverage-analyzer** - Test coverage analysis and improvement
- **qa-automation** - End-to-end quality assurance workflows

### Documentation

- **doc-generator** - Automatic documentation creation
- **api-docs** - API documentation with OpenAPI/Swagger
- **readme-builder** - Professional README generation

### Project Management

- **task-tracker** - Issue and task management integration
- **sprint-planner** - Agile sprint planning assistance
- **standup-helper** - Daily standup report generation
- **[conductor-orchestrator-superpowers](https://github.com/Ibrahim-3d/conductor-orchestrator-superpowers)** - Multi-agent orchestration with Evaluate-Loop, parallel execution, Board of Directors, 42 skills, 22 commands. One command (`/go`) handles spec, plan, execute, evaluate, and fix.

### Security

- **security-scan** (Anthropic) - Security vulnerability analysis
- **dependency-audit** - Dependency security checking
- **secrets-detector** - Find exposed secrets in code

## Creating Plugins

### Plugin Structure

```
my-plugin/
├── .claude-plugin/
│   └── plugin.json          # Plugin manifest
├── commands/                # Custom slash commands
│   ├── hello.md
│   └── build.md
├── agents/                  # Specialized subagents
│   └── feature-agent.md
├── hooks/                   # Workflow hooks
│   └── hooks.json
├── scripts/                 # Shell scripts
│   └── setup.sh
└── .mcp.json               # MCP server configuration
```

### Basic Plugin Manifest

```json
{
  "name": "my-awesome-plugin",
  "version": "1.0.0",
  "description": "Does awesome things with Claude Code",
  "author": "Your Name",
  "homepage": "https://github.com/yourusername/my-plugin",
  "repository": "https://github.com/yourusername/my-plugin",
  "license": "MIT",
  "keywords": ["development", "automation", "productivity"]
}
```

### Quick Plugin Creation

```bash
# Use the meta-plugin to create new plugins
/plugin install plugin-creator
/create-plugin my-awesome-plugin
```

## Examples

### Example 1: Simple Command Plugin

Create a greeting command:

```markdown
<!-- commands/hello.md -->
You are a friendly assistant. Greet the user warmly and ask how you can help them today.
```

```json
// .claude-plugin/plugin.json
{
  "name": "hello-plugin",
  "version": "1.0.0",
  "description": "A friendly greeting plugin"
}
```

### Example 2: Code Review Plugin

```markdown
<!-- commands/review.md -->
Perform a comprehensive code review:

1. Check for code style issues
2. Identify potential bugs
3. Suggest performance improvements
4. Verify test coverage
5. Check security vulnerabilities

Provide actionable feedback in a constructive tone.
```

### Example 3: Plugin with Hooks

```json
// hooks/hooks.json
{
  "hooks": [
    {
      "event": "before-commit",
      "script": "./scripts/lint-and-test.sh",
      "description": "Run linting and tests before commit"
    }
  ]
}
```

More examples in the [examples/](./examples) directory.

## Tutorials

- [Creating Your First Plugin](./docs/tutorials/first-plugin.md)
- [Publishing to a Marketplace](./docs/tutorials/publishing-plugins.md)
- [Advanced Plugin Architecture](./docs/tutorials/advanced-architecture.md)
- [Working with MCP Servers](./docs/tutorials/mcp-integration.md)
- [Creating Specialized Agents](./docs/tutorials/creating-agents.md)

## Community

- [Claude Developers Discord](https://anthropic.com/discord) - Official Discord community
- [GitHub Discussions](https://github.com/anthropics/claude-code/discussions) - Q&A and discussions
- [Twitter/X @AnthropicAI](https://twitter.com/AnthropicAI) - Official updates

### Contributing Plugins

Have you created a useful plugin? Share it with the community!

1. Add your plugin to a marketplace
2. Submit a PR to add it to this list
3. Share in Discord and discussions

## Contributing

Contributions are welcome! Please read the [contribution guidelines](CONTRIBUTING.md) first.

### How to Contribute

- Add new plugins to the list
- Improve documentation
- Share tutorials and guides
- Report issues with plugins
- Suggest new plugin categories

## Architecture & Technical Details

For detailed technical information:

- [Plugin Architecture](./docs/architecture/plugin-system.md)
- [Manifest Specification](./docs/architecture/manifest-spec.md)
- [Marketplace Protocol](./docs/architecture/marketplace-protocol.md)
- [Hook System](./docs/architecture/hooks.md)
- [MCP Integration](./docs/architecture/mcp-integration.md)

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

To the extent possible under law, the contributors have waived all copyright and related rights to this work.

---

**Note**: Claude Code is developed by Anthropic. This is a community-maintained collection of plugins and resources.

**Last Updated**: October 2025
