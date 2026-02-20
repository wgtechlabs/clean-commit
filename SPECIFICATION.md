# Clean Commit Specification

Version: 1.0.0

This document provides the complete technical specification for the Clean Commit workflow.

**About this workflow:** Clean Commit is a documented personal workflow I've refined over years of practice across multiple projects. It represents my standardized approach to writing commit messages. As others adopt and adapt it, it may evolve into a broader convention over time.

---

## Table of Contents

- [Format Rules](#format-rules)
- [The 9 Types](#the-9-types)
- [Decision Tree](#decision-tree)
- [Edge Cases & FAQs](#edge-cases--faqs)
- [Comparison with Other Workflows](#comparison-with-other-workflows)

---

## Format Rules

### Basic Structure

```
<emoji> <type>: <description>
```

Or with optional scope:

```
<emoji> <type> (<scope>): <description>
```

Or with breaking change marker:

```
<emoji> <type>!: <description>
```

Or with scope and breaking change marker:

```
<emoji> <type>! (<scope>): <description>
```

### Mandatory Rules

1. **Emoji**: Must be the exact emoji specified for each type
2. **Type**: Must be lowercase, one of the 9 defined types
3. **Colon**: Required after type (or scope if present)
4. **Space**: Single space after colon
5. **Description**: 
   - Present tense ("add" not "added", "fix" not "fixed")
   - Lowercase first letter
   - No period at the end
   - Maximum 72 characters (including emoji and type)
   - Clear and concise

### Optional Elements

1. **Scope**: 
   - Enclosed in parentheses
   - Space before opening parenthesis
   - Placed between type and colon
   - Lowercase
   - Single word preferred
   - Hyphenated if needed (e.g., `user-profile`)

2. **Breaking Change Marker (`!`)**:
   - A single `!` placed immediately after the type (before scope or colon)
   - Signals a breaking change in the subject line
   - Can be combined with scope: `<type>! (<scope>):`
   - Should also include `BREAKING CHANGE:` in the commit body for details
   - Does not change which type to use — use the type that best describes the change

### Examples of Correct Format

✅ Good:
```
📦 new: user authentication system
🔧 update (api): improve error handling
🗑️ remove: deprecated payment gateway
📦 new!: completely redesign authentication system
🔧 update! (api): change response format for all endpoints
```

❌ Bad:
```
new: user authentication  (missing emoji)
📦 New: authentication    (capitalized type)
📦 new: Authentication.   (capitalized description, has period)
📦 new:authentication     (missing space after colon)
📦 new: Added auth        (past tense)
📦 new(api): feature      (missing space before scope)
📦 new !(api): feature    (space before !, must be immediately after type)
```

---

## The 9 Types

### 📦 new - Adding Code

**When to use:**
- Adding new features
- Creating new files or components
- Adding new dependencies
- Introducing new functionality
- Implementing new capabilities

**Examples:**
```
📦 new: user registration with email verification
📦 new (auth): oauth2 google authentication
📦 new: real-time chat feature with websockets
📦 new (api): pagination support for all list endpoints
📦 new: dark mode toggle in settings
📦 new (database): migration for user preferences table
```

**Don't use for:**
- Updating existing features (use `update`)
- Configuration files (use `setup`)
- Documentation (use `docs`)

---

### 🔧 update - Changing Code

**When to use:**
- Modifying existing functionality
- Refactoring code
- Improving performance
- Optimizing algorithms
- Enhancing user experience
- Changing existing behavior

**Examples:**
```
🔧 update: improve login form validation
🔧 update (api): optimize database query performance
🔧 update: refactor user service to use async/await
🔧 update (ui): enhance mobile responsive design
🔧 update: replace moment.js with date-fns
🔧 update (search): improve fuzzy search algorithm
```

**Don't use for:**
- Bug fixes that are security-related (use `security`)
- Adding new features (use `new`)
- Removing functionality (use `remove`)

---

### 🗑️ remove - Removing Code

**When to use:**
- Deleting deprecated code
- Removing unused dependencies
- Eliminating obsolete features
- Cleaning up unused files
- Removing commented-out code

**Examples:**
```
🗑️ remove: deprecated legacy api endpoints
🗑️ remove (deps): unused axios dependency
🗑️ remove: obsolete user migration scripts
🗑️ remove (ui): old unused modal components
🗑️ remove: commented-out debug code
🗑️ remove (feature): beta analytics dashboard
```

**Don't use for:**
- General cleanup (use `chore`)
- Updating dependencies (use `chore`)

---

### 🔒 security - Security Fixes

**When to use:**
- Fixing security vulnerabilities
- Patching security issues
- Addressing CVEs
- Fixing authentication/authorization bugs
- Preventing security exploits (XSS, CSRF, SQL injection, etc.)
- Updating dependencies due to security advisories

**Examples:**
```
🔒 security: patch sql injection vulnerability in search
🔒 security (auth): fix jwt token validation bypass
🔒 security: sanitize user input to prevent xss attacks
🔒 security (api): add rate limiting to prevent ddos
🔒 security: update lodash to fix prototype pollution
🔒 security (session): implement secure cookie flags
```

**Don't use for:**
- Regular bug fixes (use `update`)
- Adding security features (use `new`)
- General dependency updates (use `chore`)

---

### ⚙️ setup - Project Configuration

**When to use:**
- Adding/modifying build configurations
- Setting up CI/CD pipelines
- Configuring development tools
- Adding linters, formatters
- Docker/container configuration
- Environment setup
- Project scaffolding

**Examples:**
```
⚙️ setup: add prettier configuration
⚙️ setup (ci): configure github actions for testing
⚙️ setup: initialize typescript project
⚙️ setup (docker): add docker compose for local development
⚙️ setup: configure eslint with airbnb style guide
⚙️ setup (build): optimize webpack production config
```

**Don't use for:**
- Code changes (use appropriate type)
- Dependency updates (use `chore`)

---

### ☕ chore - Maintenance

**When to use:**
- Routine maintenance tasks
- Updating dependencies (non-security)
- Cleaning up code
- Reorganizing file structure
- Formatting code
- Updating tooling
- Build process improvements
- General housekeeping

**Examples:**
```
☕ chore: update npm dependencies to latest versions
☕ chore (deps): bump react from 17.0.2 to 18.2.0
☕ chore: reorganize component folder structure
☕ chore: format codebase with prettier
☕ chore (package): remove unused npm scripts
☕ chore: clean up console.log statements
```

**Don't use for:**
- New features (use `new`)
- Bug fixes (use `update`)
- Security updates (use `security`)

---

### 🧪 test - Testing

**When to use:**
- Adding new tests
- Updating existing tests
- Fixing failing tests
- Improving test coverage
- Adding test utilities
- Configuring test frameworks
- Refactoring tests

**Examples:**
```
🧪 test: add unit tests for authentication service
🧪 test (api): integration tests for user endpoints
🧪 test: fix flaky date parsing test
🧪 test (e2e): add cypress tests for login flow
🧪 test: increase coverage for payment module
🧪 test (utils): add test helpers for mocking api calls
```

**Don't use for:**
- Test configuration setup (use `setup`)
- Non-test code changes

---

### 📖 docs - Documentation

**When to use:**
- Adding/updating README
- Writing code comments
- Creating/updating guides
- Documenting APIs
- Updating inline documentation
- Creating tutorials
- Fixing documentation typos

**Examples:**
```
📖 docs: update installation instructions
📖 docs (api): add swagger documentation for auth endpoints
📖 docs: fix typos in contributing guide
📖 docs (readme): add usage examples
📖 docs: create architecture decision record for state management
📖 docs (code): add jsdoc comments to utility functions
```

**Don't use for:**
- Code changes (even if documenting them)
- Configuration changes (use `setup`)

---

### 🚀 release - Version Releases

**When to use:**
- Marking version releases
- Preparing releases
- Creating release candidates
- Publishing packages
- Version bumps for releases
- Hotfix releases

**Examples:**
```
🚀 release: version 1.0.0
🚀 release: prepare for version 2.1.0 release
🚀 release: hotfix version 1.0.1
🚀 release (npm): publish package version 3.2.0
🚀 release: release candidate 2.0.0-rc.1
🚀 release: bump version to 1.5.0 for production
```

**Don't use for:**
- Regular commits
- Pre-release development work

---

## Decision Tree

Use this flowchart to choose the right commit type:

```
Is this a version release/tag?
├─ Yes → 🚀 release
└─ No ↓

Is this a security fix/patch?
├─ Yes → 🔒 security
└─ No ↓

Is this ONLY documentation?
├─ Yes → 📖 docs
└─ No ↓

Is this ONLY test-related?
├─ Yes → 🧪 test
└─ No ↓

Is this project config/tooling/CI?
├─ Yes → ⚙️ setup
└─ No ↓

Are you removing code/features/deps?
├─ Yes → 🗑️ remove
└─ No ↓

Are you adding NEW functionality?
├─ Yes → 📦 new
└─ No ↓

Are you changing EXISTING code?
├─ Yes → 🔧 update
└─ No ↓

Is this maintenance/deps/cleanup?
└─ Yes → ☕ chore
```

### Quick Decision Guide

**Ask yourself:**
1. "Am I releasing a version?" → `release`
2. "Is this fixing a security issue?" → `security`
3. "Am I only changing docs?" → `docs`
4. "Am I only working on tests?" → `test`
5. "Am I configuring tools/CI/build?" → `setup`
6. "Am I deleting something?" → `remove`
7. "Does this functionality exist yet?" 
   - No → `new`
   - Yes → `update`
8. "Is this just maintenance?" → `chore`

---

## Edge Cases & FAQs

### Q: What if my commit does multiple things?

**A:** Your commit should do only one thing. If you're tempted to use multiple types, split it into separate commits.

❌ Bad:
```
📦 new: add user service and update api documentation
```

✅ Good:
```
📦 new: user service with crud operations
📖 docs(api): document user service endpoints
```

### Q: Is it `new` or `update` when adding to existing code?

**A:** 
- **Use `new`** if you're adding a new capability that didn't exist
- **Use `update`** if you're modifying how existing functionality works

Examples:
```
📦 new: add forgot password feature          (new capability)
🔧 update: improve existing login validation (modifying existing)
```

### Q: When to use `chore` vs `setup`?

**A:**
- **`setup`**: One-time configuration or initial tooling setup
- **`chore`**: Ongoing maintenance and updates

Examples:
```
⚙️ setup: initialize eslint configuration    (first time)
☕ chore: update eslint rules               (maintenance)
```

### Q: What about bug fixes?

**A:** 
- **Security bugs** → `security`
- **All other bugs** → `update` (you're updating broken code to work correctly)

Examples:
```
🔒 security: fix authentication bypass bug
🔧 update: fix date formatting in user profile
```

### Q: Can I use custom emojis or types?

**A:** No. This workflow defines exactly 9 types with specific emojis. Consistency is key to making commit history scannable.

### Q: What about breaking changes?

**A:** Use `!` after the type in the subject line to signal a breaking change. You can also add `BREAKING CHANGE:` in the commit body for additional detail.

**Subject-line marker only:**
```
📦 new!: completely redesign authentication system
🔧 update! (api): change response format for all endpoints
🗑️ remove!: remove deprecated v1 api endpoints
```

**With body detail:**
```
🔧 update! (api): change authentication endpoint response format

BREAKING CHANGE: Authentication endpoint now returns user object instead of token string.
```

Both approaches are valid and can be combined. The `!` marker makes breaking changes immediately visible when scanning history, while the `BREAKING CHANGE:` body note provides detail. The `BREAKING CHANGE:` body note alone (without `!`) remains supported for backwards compatibility.

### Q: Should I use scopes for small projects?

**A:** Scopes are optional. For small projects, they often add unnecessary complexity. Use them when they add clarity.

### Q: What if I'm doing multiple types of work in different files?

**A:** Split into multiple commits. Each commit should represent one logical change.

---

## Comparison with Other Workflows

### vs. Conventional Commits

**Conventional Commits:**
- Types: `feat`, `fix`, `docs`, `style`, `refactor`, `perf`, `test`, `build`, `ci`, `chore`, `revert`
- More types to remember (11+)
- Text-only (no emojis)
- More rigid structure

**Clean Commit:**
- Only 9 types
- Visual emoji makes scanning easier
- Simpler, more intuitive type names
- Combines related types (e.g., `build` + `ci` = `setup`)
- Supports `!` breaking change marker for subject-line visibility

### vs. Gitmoji

**Gitmoji:**
- 60+ different emojis
- Emoji-first approach
- No standardized type keywords
- High cognitive load

**Clean Commit:**
- Only 9 emojis
- Emoji + type keyword for clarity
- Easy to remember
- Balanced between visual and text

### Why Clean Commit?

Clean Commit takes the best of both worlds:
- ✅ Visual benefits of emojis (like Gitmoji)
- ✅ Structured format (like Conventional Commits)  
- ✅ Minimal cognitive load (unlike both)
- ✅ Universal and simple

---

## Summary

Clean Commit is designed to be:
- **Simple**: Only 9 types to remember
- **Visual**: Emojis make history scannable
- **Flexible**: Works for any project
- **Clear**: Obvious which type to use
- **Universal**: Not tied to any specific tool or workflow

**Remember:** Clean Code deserves Clean Commit.

---

*For quick reference, see [QUICK-REFERENCE.md](QUICK-REFERENCE.md)*
