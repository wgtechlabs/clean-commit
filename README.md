# Clean Commit

> **Clean Code deserves Clean Commit.**

<!-- Banner placeholder - Add project banner here -->

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Version](https://img.shields.io/badge/version-1.0.0-green.svg)](https://github.com/wgtechlabs/clean-commit)

A minimalist git commit convention designed to be simple, memorable, and universal. Clean Commit helps you write clear, consistent commit messages that make your project history easy to understand.

---

## Why Clean Commit?

Existing commit conventions are **too complex**. They require memorizing lengthy type names, complex scoping rules, and rigid formats that slow you down.

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

## Learn More

- 📋 [**SPECIFICATION.md**](SPECIFICATION.md) - Full technical specification with detailed guidelines
- 📄 [**QUICK-REFERENCE.md**](QUICK-REFERENCE.md) - Single-page cheatsheet for quick lookup
- 💡 [**examples/EXAMPLES.md**](examples/EXAMPLES.md) - Real-world examples by project type

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
