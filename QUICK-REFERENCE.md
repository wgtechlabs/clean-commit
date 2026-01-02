# Clean Commit Quick Reference

**One-page cheatsheet for Clean Commit workflow**

---

## Format

```
<emoji> <type>: <description>
<emoji> <type>(<scope>): <description>  [with optional scope]
```

---

## The 9 Types

| Emoji | Type | Use For |
|:-----:|------|---------|
| 📦 | `new` | Adding code, features, files |
| 🔧 | `update` | Changing existing code, refactoring |
| 🗑️ | `remove` | Removing code, files, features |
| 🔒 | `security` | Security fixes, patches, vulnerabilities |
| ⚙️ | `setup` | Project configs, CI/CD, tooling |
| ☕ | `chore` | Maintenance, dependencies, housekeeping |
| 🧪 | `test` | Test changes and additions |
| 📖 | `docs` | Documentation updates |
| 🚀 | `release` | Version releases |

---

## Quick Decision Flowchart

```
Releasing a version?        → 🚀 release
Security fix?               → 🔒 security
Only docs?                  → 📖 docs
Only tests?                 → 🧪 test
Config/CI/tooling?          → ⚙️ setup
Removing something?         → 🗑️ remove
Adding new functionality?   → 📦 new
Changing existing code?     → 🔧 update
Maintenance/cleanup?        → ☕ chore
```

---

## Copy-Paste Examples

### 📦 new
```
📦 new: user authentication system
📦 new(api): endpoint for user registration
📦 new: dark mode support
```

### 🔧 update
```
🔧 update: improve database query performance
🔧 update(ui): enhance button animations
🔧 update: refactor payment processing
```

### 🗑️ remove
```
🗑️ remove: deprecated api endpoints
🗑️ remove(deps): unused lodash dependency
🗑️ remove: obsolete migration scripts
```

### 🔒 security
```
🔒 security: patch xss vulnerability
🔒 security(auth): fix jwt validation
🔒 security: update dependencies with cves
```

### ⚙️ setup
```
⚙️ setup: add eslint configuration
⚙️ setup(ci): configure github actions
⚙️ setup: initialize docker environment
```

### ☕ chore
```
☕ chore: update npm dependencies
☕ chore(deps): bump react to v18
☕ chore: clean up unused imports
```

### 🧪 test
```
🧪 test: add unit tests for auth service
🧪 test(api): integration tests for users
🧪 test: fix flaky date parsing test
```

### 📖 docs
```
📖 docs: update installation guide
📖 docs(api): add endpoint documentation
📖 docs: fix typos in readme
```

### 🚀 release
```
🚀 release: version 1.0.0
🚀 release: prepare for v2.1.0
🚀 release: hotfix version 1.0.1
```

---

## Rules Checklist

- ✅ Emoji matches the type
- ✅ Type is lowercase
- ✅ Space after colon
- ✅ Present tense description
- ✅ Lowercase first letter of description
- ✅ No period at end
- ✅ Under 72 characters total

---

## Scope Guidelines

**Optional but useful for larger projects**

Good scopes:
- Component: `(header)`, `(footer)`, `(navbar)`
- Module: `(api)`, `(database)`, `(auth)`
- Feature: `(payments)`, `(notifications)`

Keep scopes:
- Short (prefer one word)
- Lowercase
- Consistent across project

---

## Git Message Template

Create a `.gitmessage` file in your project:

```
# <emoji> <type>(<scope>): <description>
# 
# Types:
# 📦 new       - Adding code
# 🔧 update    - Changing code
# 🗑️ remove    - Removing code
# 🔒 security  - Security fixes
# ⚙️ setup     - Project configs
# ☕ chore     - Maintenance
# 🧪 test      - Tests
# 📖 docs      - Documentation
# 🚀 release   - Version releases
#
# Rules:
# - Use present tense
# - Lowercase type and description
# - No period at end
# - Max 72 chars
#
# Example: 📦 new(auth): user login with email verification
```

### Set up the template globally:

```bash
git config --global commit.template ~/.gitmessage
```

### Or per project:

```bash
git config commit.template .gitmessage
```

---

## Common Patterns

### Dependency Updates
```
☕ chore(deps): bump express from 4.17.1 to 4.18.2
☕ chore: update all dev dependencies
🔒 security: update lodash to fix vulnerability
```

### Refactoring
```
🔧 update: refactor user service to use async/await
🔧 update(api): simplify error handling middleware
🔧 update: extract validation logic to utils
```

### Adding Features
```
📦 new: real-time notifications with websockets
📦 new(api): pagination support for all endpoints
📦 new: export data to csv functionality
```

### Bug Fixes
```
🔧 update: fix date formatting in profile
🔧 update(api): handle null values in response
🔒 security: fix auth token validation bypass
```

### Testing
```
🧪 test: add e2e tests for checkout flow
🧪 test(unit): increase coverage for utils
🧪 test: mock external api in integration tests
```

---

## Tips

1. **One commit = One logical change**
   - Don't mix types in one commit
   - Split unrelated changes

2. **Write for humans**
   - Be clear and descriptive
   - Think: "What did this commit accomplish?"

3. **Be consistent**
   - Stick to the workflow
   - Use the same scope names

4. **When in doubt, check the decision tree**
   - Start from top (release? security?)
   - Work your way down

---

## Need More Details?

- 📋 [Full Specification](SPECIFICATION.md)
- 💡 [Real-World Examples](examples/EXAMPLES.md)
- 📖 [Main README](README.md)

---

<p align="center">
  <strong>Clean Code deserves Clean Commit.</strong>
</p>
