# Real-World Examples

This document shows real-world commit examples organized by project type to help you apply Clean Commit to your projects.

---

## Table of Contents

- [Web Application](#web-application)
- [API / Backend](#api--backend)
- [Library / SDK](#library--sdk)
- [CLI Tool](#cli-tool)
- [Bot (Discord/Telegram)](#bot-discordtelegram)
- [GitHub Action](#github-action)

---

## Web Application

**Context:** A full-stack web app with React frontend and Node.js backend

### Feature Development
```
📦 new: user profile page with avatar upload
📦 new(auth): social login with google and github
📦 new(dashboard): real-time analytics widgets
🔧 update(ui): improve mobile responsive layout
🔧 update: optimize image loading with lazy loading
🗑️ remove(ui): deprecated jquery legacy code
```

### Bug Fixes & Improvements
```
🔧 update: fix cart total calculation rounding error
🔧 update(form): improve validation error messages
🔧 update(api): handle network timeout gracefully
🔒 security: sanitize html input to prevent xss
🔒 security(session): implement csrf token validation
```

### Testing & Documentation
```
🧪 test(e2e): add cypress tests for checkout flow
🧪 test: increase coverage for payment module
📖 docs: update component usage examples
📖 docs(api): document authentication flow
```

### Maintenance
```
☕ chore(deps): bump react from 17.0.2 to 18.2.0
☕ chore: update webpack to version 5
⚙️ setup(ci): add automated deployment pipeline
⚙️ setup: configure storybook for components
```

### Release
```
🚀 release: version 2.0.0
🚀 release: hotfix version 2.0.1 for login bug
```

---

## API / Backend

**Context:** RESTful API service with database and authentication

### API Development
```
📦 new(api): user registration endpoint with validation
📦 new: rate limiting middleware for api protection
📦 new(db): migration for orders table
📦 new(auth): jwt token refresh mechanism
🔧 update(api): improve error response format
🔧 update: optimize database query with indexing
🔧 update(middleware): refactor logging to use winston
```

### Security & Performance
```
🔒 security(api): add input validation to prevent injection
🔒 security: hash passwords with bcrypt instead of md5
🔒 security(auth): fix authorization bypass in admin routes
🔧 update: implement connection pooling for database
🔧 update(cache): add redis caching for frequent queries
```

### Database & Infrastructure
```
📦 new(db): add full-text search indexes
🔧 update(db): optimize user query performance
🗑️ remove(db): drop unused legacy tables
⚙️ setup(docker): containerize application with compose
⚙️ setup: configure automated database backups
```

### Testing & Documentation
```
🧪 test(api): integration tests for auth endpoints
🧪 test: add load testing with artillery
📖 docs(api): generate swagger documentation
📖 docs: add architecture decision records
```

### Maintenance & Release
```
☕ chore(deps): update express to latest security patch
☕ chore: clean up deprecated api endpoints
🚀 release: version 3.1.0 with new features
```

---

## Library / SDK

**Context:** JavaScript/TypeScript library for developers

### Library Features
```
📦 new: add async/await support to all methods
📦 new(api): client method for batch operations
📦 new: typescript type definitions
🔧 update: improve error handling with custom errors
🔧 update: refactor core module for better performance
🗑️ remove: deprecated callback-based api
```

### API Changes
```
🔧 update(api): simplify configuration options
🔧 update: change default timeout to 30 seconds
📖 docs(breaking): document v3 migration guide
🚀 release: version 3.0.0 with breaking changes
```

### Developer Experience
```
📦 new: add debug mode for troubleshooting
🔧 update: improve error messages with actionable hints
📖 docs: add interactive examples to readme
📖 docs(api): document all public methods with jsdoc
📖 docs: create getting started tutorial
```

### Testing & Quality
```
🧪 test: add unit tests for all core modules
🧪 test: achieve 95% code coverage
⚙️ setup: configure automatic type checking
⚙️ setup(ci): add automated npm publishing
☕ chore: update dependencies to latest stable
```

### Distribution
```
📦 new: add esm module support
📦 new: add umd bundle for browsers
⚙️ setup(build): optimize bundle size with rollup
🚀 release: publish version 2.5.0 to npm
```

---

## CLI Tool

**Context:** Command-line tool built with Node.js

### Commands & Features
```
📦 new: add init command for project setup
📦 new(cmd): deploy command with progress bar
📦 new: interactive configuration wizard
🔧 update(cli): improve help text formatting
🔧 update: add colorized output for better readability
🗑️ remove: deprecated --legacy flag
```

### User Experience
```
📦 new: add autocomplete support for bash and zsh
📦 new(ui): spinner animation for long operations
🔧 update: improve error messages with suggestions
🔧 update(config): support yaml and json config files
📖 docs: add command examples to help text
```

### Installation & Distribution
```
⚙️ setup: add installation script for multiple platforms
⚙️ setup(ci): automate binary builds for releases
📦 new: support installation via homebrew
📦 new: add windows installer
🚀 release: version 1.0.0 stable release
```

### Testing & Debugging
```
🧪 test: add integration tests for all commands
🧪 test(cmd): test deploy command with mocked api
📦 new(debug): add verbose flag for troubleshooting
☕ chore(deps): update commander to latest version
```

### Documentation
```
📖 docs: create comprehensive usage guide
📖 docs(examples): add real-world workflow examples
📖 docs: add troubleshooting section
📖 docs(install): platform-specific installation guides
```

---

## Bot (Discord/Telegram)

**Context:** Chat bot with commands and event handlers

### Bot Commands
```
📦 new(cmd): welcome command for new members
📦 new: moderation commands for admins
📦 new(cmd): poll creation with reaction voting
🔧 update: improve help command with categories
🔧 update(cmd): enhance music player with queue system
🗑️ remove: deprecated legacy command syntax
```

### Features & Integrations
```
📦 new: integration with spotify api
📦 new(feature): automated role assignment
📦 new: custom embed messages with rich formatting
🔧 update: improve message parsing and validation
🔧 update(db): migrate to postgresql for better scaling
```

### Event Handlers
```
📦 new(event): handle member join events
📦 new: reaction role system
🔧 update(event): improve message deletion logging
🔧 update: add rate limiting for command usage
🔒 security: validate user permissions before commands
```

### Configuration & Deployment
```
⚙️ setup: add environment variable configuration
⚙️ setup(deploy): containerize bot with docker
📦 new(config): per-server configuration system
☕ chore: update discord.js to latest version
```

### Testing & Documentation
```
🧪 test: add unit tests for command handlers
🧪 test: mock discord api for integration tests
📖 docs: create bot setup guide for server admins
📖 docs(commands): document all available commands
🚀 release: deploy version 2.0.0 to production
```

---

## GitHub Action

**Context:** Custom GitHub Action for CI/CD workflows

### Action Development
```
📦 new: initial action for code quality checks
📦 new(input): add customizable threshold options
📦 new: support for multiple programming languages
🔧 update: improve performance of file scanning
🔧 update(output): add detailed report generation
🗑️ remove: legacy node 12 support
```

### Integration & Compatibility
```
📦 new: add support for pull request comments
📦 new(integration): slack notification output
🔧 update: support both github token and app auth
🔧 update: improve error handling with actionable messages
⚙️ setup(ci): add automated testing workflow
```

### Documentation & Examples
```
📖 docs: create comprehensive action usage guide
📖 docs(examples): add workflow examples for common scenarios
📖 docs: add troubleshooting section
📖 docs(inputs): document all input parameters
📖 docs(outputs): document all output values
```

### Distribution & Versioning
```
⚙️ setup: configure automated release process
⚙️ setup(build): optimize action bundle size
🚀 release: version 1.0.0 stable release
🚀 release: tag v2 for breaking changes
☕ chore(deps): update action dependencies
```

### Testing & Quality
```
🧪 test: add end-to-end tests with real workflows
🧪 test(unit): test action logic with various inputs
🔒 security: validate and sanitize user inputs
☕ chore: update action to use node 20
```

---

## Tips for Your Project

### Start Simple
Begin with just the basic format. Add scopes only when your project grows and needs them.

### Be Consistent
Choose scope names early and stick to them across your team.

### Review History
Periodically review your commit history to ensure consistency and adjust scope strategy if needed.

### Team Alignment
Share this guide with your team and agree on scope conventions for your specific project.

---

## More Resources

- 📋 [Full Specification](../SPECIFICATION.md) - Detailed rules and guidelines
- 📄 [Quick Reference](../QUICK-REFERENCE.md) - One-page cheatsheet
- 📖 [Main README](../README.md) - Overview and introduction

---

<p align="center">
  <strong>Clean Code deserves Clean Commit.</strong>
</p>
