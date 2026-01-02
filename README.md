# Clean Commit

> **Clean Code deserves Clean Commit.**

<!-- Banner placeholder - Add project banner here -->

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Version](https://img.shields.io/badge/version-1.0.0-green.svg)](https://github.com/wgtechlabs/clean-commit)

A minimalist git commit workflow designed to be simple, memorable, and universal. Clean Commit helps you write clear, consistent commit messages that make your project history easy to understand.

**Note:** This is a documented personal workflow I've refined over years of practice. While I use the term "Clean Commit workflow" to describe this standardized approach, it may evolve into a broader convention as others adopt and adapt it.

---

## Why Clean Commit?

Existing commit workflows are **too complex**. They require memorizing lengthy type names, complex scoping rules, and rigid formats that slow you down.

Clean Commit is different:
- ✨ **Simple**: Only 9 types to remember
- 🎯 **Visual**: Emoji makes scanning history effortless
- 📝 **Flexible**: Works for any project size or type
- 🚀 **Fast**: No overthinking - just commit

---

## The 9 Types

| Emoji | Type | What it covers |
|:-----:|------|----------------|
| 📦 | `new` | Adding new features, files, or capabilities |
| 🔧 | `update` | Changing existing code, refactoring, improvements |
| 🗑️ | `remove` | Removing code, files, features, or dependencies |
| 🔒 | `security` | Security fixes, patches, vulnerability resolutions |
| ⚙️ | `setup` | Project configs, CI/CD, tooling, build systems |
| ☕ | `chore` | Maintenance tasks, dependency updates, housekeeping |
| 🧪 | `test` | Adding, updating, or fixing tests |
| 📖 | `docs` | Documentation changes and updates |
| 🚀 | `release` | Version releases and release preparation |

---

## Quick Start

### Basic Format

```
<emoji> <type>: <description>
```

**Example:**
```
📦 new: user authentication system
```

### With Optional Scope

```
<emoji> <type>(<scope>): <description>
```

**Example:**
```
🔧 update(api): improve error handling
```

### Rules
- Use lowercase for type
- Use present tense ("add" not "added")
- No period at the end
- Keep description under 72 characters

---

## Examples

### 📦 new - Adding Code
```
📦 new: login page with email validation
📦 new(api): endpoint for user registration
📦 new: dark mode theme support
```

### 🔧 update - Changing Code
```
🔧 update: improve database query performance
🔧 update(ui): enhance button hover animations
🔧 update: refactor payment processing logic
```

### 🗑️ remove - Removing Code
```
🗑️ remove: deprecated legacy authentication
🗑️ remove(deps): unused lodash dependency
🗑️ remove: obsolete migration scripts
```

### 🔒 security - Security Fixes
```
🔒 security: patch XSS vulnerability in user input
🔒 security(auth): fix JWT token validation
🔒 security: update dependencies with known CVEs
```

### ⚙️ setup - Project Configuration
```
⚙️ setup: add eslint configuration
⚙️ setup(ci): configure github actions workflow
⚙️ setup: initialize docker compose environment
```

### ☕ chore - Maintenance
```
☕ chore: update npm dependencies
☕ chore(deps): bump react to version 18
☕ chore: clean up unused imports
```

### 🧪 test - Testing
```
🧪 test: add unit tests for auth service
🧪 test(api): integration tests for user endpoints
🧪 test: fix flaky date parsing test
```

### 📖 docs - Documentation
```
📖 docs: update installation instructions
📖 docs(api): add endpoint documentation
📖 docs: fix typos in contributing guide
```

### 🚀 release - Version Releases
```
🚀 release: version 1.0.0
🚀 release: prepare for 2.1.0 release
🚀 release: hotfix version 1.0.1
```

---

## Optional Scope

Scopes help specify **where** the change happened. They're completely optional but helpful in larger projects.

**Good scopes:**
- Component names: `(header)`, `(footer)`, `(navbar)`
- Module names: `(api)`, `(database)`, `(auth)`
- Feature areas: `(payments)`, `(notifications)`, `(search)`

**Keep scopes:**
- Short (one word when possible)
- Lowercase
- Consistent across your project

---

## GitHub Copilot Integration

Automate Clean Commit in VS Code by configuring GitHub Copilot to generate commit messages following this workflow.

### Setup Instructions

1. Open VS Code Settings (JSON): `Ctrl/Cmd + Shift + P` → "Preferences: Open User Settings (JSON)"
2. Add this configuration:

```json
{
  "github.copilot.chat.commitMessageGeneration.instructions": [
    {
      "text": "Use Clean Commit workflow: <emoji> <type>: <description> or <emoji> <type>(<scope>): <description>. Choose type: 📦 new=user-facing features/functionality, 🔧 update=modify existing code/logic, 🗑️ remove=delete code/features, 🔒 security=fix vulnerabilities, ⚙️ setup=configs/CI/tooling/.github files, ☕ chore=maintenance/deps/LICENSE, 🧪 test=test files, 📖 docs=README/guides/comments, 🚀 release=version tags. Format: lowercase type, present tense (add not added), no period, max 72 chars. Examples: ⚙️ setup: add GitHub funding configuration | 📦 new: user authentication | 🔧 update(api): improve error handling | ☕ chore(deps): bump react version"
    }
  ]
}
```

3. Save and reload VS Code
4. GitHub Copilot will now suggest commit messages using Clean Commit format

**Alternative: Project-Specific Setup**

Create `.github/copilot-instructions.md` in your repository:

```markdown
# Commit Message Workflow

Use Clean Commit workflow for all commits.
See: https://github.com/wgtechlabs/clean-commit
```

---

## Real-World Examples

This section shows real-world commit examples organized by project type to help you apply Clean Commit to your projects.

### Web Application

**Context:** A full-stack web app with React frontend and Node.js backend

#### Feature Development
```
📦 new: user profile page with avatar upload
📦 new(auth): social login with google and github
📦 new(dashboard): real-time analytics widgets
🔧 update(ui): improve mobile responsive layout
🔧 update: optimize image loading with lazy loading
🗑️ remove(ui): deprecated jquery legacy code
```

#### Bug Fixes & Improvements
```
🔧 update: fix cart total calculation rounding error
🔧 update(form): improve validation error messages
🔧 update(api): handle network timeout gracefully
🔒 security: sanitize html input to prevent xss
🔒 security(session): implement csrf token validation
```

#### Testing & Documentation
```
🧪 test(e2e): add cypress tests for checkout flow
🧪 test: increase coverage for payment module
📖 docs: update component usage examples
📖 docs(api): document authentication flow
```

#### Maintenance
```
☕ chore(deps): bump react from 17.0.2 to 18.2.0
☕ chore: update webpack to version 5
⚙️ setup(ci): add automated deployment pipeline
⚙️ setup: configure storybook for components
```

#### Release
```
🚀 release: version 2.0.0
🚀 release: hotfix version 2.0.1 for login bug
```

### API / Backend

**Context:** RESTful API service with database and authentication

#### API Development
```
📦 new(api): user registration endpoint with validation
📦 new: rate limiting middleware for api protection
📦 new(db): migration for orders table
📦 new(auth): jwt token refresh mechanism
🔧 update(api): improve error response format
🔧 update: optimize database query with indexing
🔧 update(middleware): refactor logging to use winston
```

#### Security & Performance
```
🔒 security(api): add input validation to prevent injection
🔒 security: hash passwords with bcrypt instead of md5
🔒 security(auth): fix authorization bypass in admin routes
🔧 update: implement connection pooling for database
🔧 update(cache): add redis caching for frequent queries
```

#### Database & Infrastructure
```
📦 new(db): add full-text search indexes
🔧 update(db): optimize user query performance
🗑️ remove(db): drop unused legacy tables
⚙️ setup(docker): containerize application with compose
⚙️ setup: configure automated database backups
```

#### Testing & Documentation
```
🧪 test(api): integration tests for auth endpoints
🧪 test: add load testing with artillery
📖 docs(api): generate swagger documentation
📖 docs: add architecture decision records
```

#### Maintenance & Release
```
☕ chore(deps): update express to latest security patch
☕ chore: clean up deprecated api endpoints
🚀 release: version 3.1.0 with new features
```

### Library / SDK

**Context:** JavaScript/TypeScript library for developers

#### Library Features
```
📦 new: add async/await support to all methods
📦 new(api): client method for batch operations
📦 new: typescript type definitions
🔧 update: improve error handling with custom errors
🔧 update: refactor core module for better performance
🗑️ remove: deprecated callback-based api
```

#### API Changes
```
🔧 update(api): simplify configuration options
🔧 update: change default timeout to 30 seconds
📖 docs(breaking): document v3 migration guide
🚀 release: version 3.0.0 with breaking changes
```

#### Developer Experience
```
📦 new: add debug mode for troubleshooting
🔧 update: improve error messages with actionable hints
📖 docs: add interactive examples to readme
📖 docs(api): document all public methods with jsdoc
📖 docs: create getting started tutorial
```

#### Testing & Quality
```
🧪 test: add unit tests for all core modules
🧪 test: achieve 95% code coverage
⚙️ setup: configure automatic type checking
⚙️ setup(ci): add automated npm publishing
☕ chore: update dependencies to latest stable
```

#### Distribution
```
📦 new: add esm module support
📦 new: add umd bundle for browsers
⚙️ setup(build): optimize bundle size with rollup
🚀 release: publish version 2.5.0 to npm
```

### CLI Tool

**Context:** Command-line tool built with Node.js

#### Commands & Features
```
📦 new: add init command for project setup
📦 new(cmd): deploy command with progress bar
📦 new: interactive configuration wizard
🔧 update(cli): improve help text formatting
🔧 update: add colorized output for better readability
🗑️ remove: deprecated --legacy flag
```

#### User Experience
```
📦 new: add autocomplete support for bash and zsh
📦 new(ui): spinner animation for long operations
🔧 update: improve error messages with suggestions
🔧 update(config): support yaml and json config files
📖 docs: add command examples to help text
```

#### Installation & Distribution
```
⚙️ setup: add installation script for multiple platforms
⚙️ setup(ci): automate binary builds for releases
📦 new: support installation via homebrew
📦 new: add windows installer
🚀 release: version 1.0.0 stable release
```

#### Testing & Debugging
```
🧪 test: add integration tests for all commands
🧪 test(cmd): test deploy command with mocked api
📦 new(debug): add verbose flag for troubleshooting
☕ chore(deps): update commander to latest version
```

#### Documentation
```
📖 docs: create comprehensive usage guide
📖 docs(examples): add real-world workflow examples
📖 docs: add troubleshooting section
📖 docs(install): platform-specific installation guides
```

### Bot (Discord/Telegram)

**Context:** Chat bot with commands and event handlers

#### Bot Commands
```
📦 new(cmd): welcome command for new members
📦 new: moderation commands for admins
📦 new(cmd): poll creation with reaction voting
🔧 update: improve help command with categories
🔧 update(cmd): enhance music player with queue system
🗑️ remove: deprecated legacy command syntax
```

#### Features & Integrations
```
📦 new: integration with spotify api
📦 new(feature): automated role assignment
📦 new: custom embed messages with rich formatting
🔧 update: improve message parsing and validation
🔧 update(db): migrate to postgresql for better scaling
```

#### Event Handlers
```
📦 new(event): handle member join events
📦 new: reaction role system
🔧 update(event): improve message deletion logging
🔧 update: add rate limiting for command usage
🔒 security: validate user permissions before commands
```

#### Configuration & Deployment
```
⚙️ setup: add environment variable configuration
⚙️ setup(deploy): containerize bot with docker
📦 new(config): per-server configuration system
☕ chore: update discord.js to latest version
```

#### Testing & Documentation
```
🧪 test: add unit tests for command handlers
🧪 test: mock discord api for integration tests
📖 docs: create bot setup guide for server admins
📖 docs(commands): document all available commands
🚀 release: deploy version 2.0.0 to production
```

### GitHub Action

**Context:** Custom GitHub Action for CI/CD workflows

#### Action Development
```
📦 new: initial action for code quality checks
📦 new(input): add customizable threshold options
📦 new: support for multiple programming languages
🔧 update: improve performance of file scanning
🔧 update(output): add detailed report generation
🗑️ remove: legacy node 12 support
```

#### Integration & Compatibility
```
📦 new: add support for pull request comments
📦 new(integration): slack notification output
🔧 update: support both github token and app auth
🔧 update: improve error handling with actionable messages
⚙️ setup(ci): add automated testing workflow
```

#### Documentation & Examples
```
📖 docs: create comprehensive action usage guide
📖 docs(examples): add workflow examples for common scenarios
📖 docs: add troubleshooting section
📖 docs(inputs): document all input parameters
📖 docs(outputs): document all output values
```

#### Distribution & Versioning
```
⚙️ setup: configure automated release process
⚙️ setup(build): optimize action bundle size
🚀 release: version 1.0.0 stable release
🚀 release: tag v2 for breaking changes
☕ chore(deps): update action dependencies
```

#### Testing & Quality
```
🧪 test: add end-to-end tests with real workflows
🧪 test(unit): test action logic with various inputs
🔒 security: validate and sanitize user inputs
☕ chore: update action to use node 20
```

---

## AI Integration

Copy these templates to integrate Clean Commit with AI coding assistants.

### GitHub Copilot

Copy [`examples/copilot.instructions.md`](examples/copilot.instructions.md) to your project:

```bash
mkdir -p .github/instructions
curl -o .github/instructions/copilot.instructions.md https://raw.githubusercontent.com/wgtechlabs/clean-commit/main/examples/copilot.instructions.md
```

### AI Agents (Codex, Claude, Cursor, Windsurf, etc.)

Copy [`examples/AGENTS.md`](examples/AGENTS.md) to your project root:

```bash
curl -o AGENTS.md https://raw.githubusercontent.com/wgtechlabs/clean-commit/main/examples/AGENTS.md
```

### Real-World Implementation

- [wgtechlabs/nuvex](https://github.com/wgtechlabs/nuvex/blob/main/.github/instructions/clean_commit.instructions.md)

---

## Learn More

- 📋 [**SPECIFICATION.md**](SPECIFICATION.md) - Full technical specification with detailed guidelines
- 📄 [**QUICK-REFERENCE.md**](QUICK-REFERENCE.md) - Single-page cheatsheet for quick lookup

---

## Contributing

We welcome contributions! Please read our [Contributing Guidelines](CONTRIBUTING.md) to get started.

---

## License

MIT License - see the [LICENSE](LICENSE) file for details.

---

## Credits

Created with ❤️ by **[Waren Gonzaga](https://github.com/warengonzaga)** / **[WG Tech Labs](https://github.com/wgtechlabs)**

---

<p align="center">
  <strong>Clean Code deserves Clean Commit.</strong>
</p>
