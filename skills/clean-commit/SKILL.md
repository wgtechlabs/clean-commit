---
name: clean-commit
description: Draft, validate, or create Clean Commit messages from Git changes when the repository adopts Clean Commit or the user requests it. Preserve other repositories' required commit conventions and distinguish drafting from committing.
---

# Clean Commit

Write one clear message for one logical change. This skill works without
Clean Workflow or any other skill. Git is needed to inspect or commit local
changes; validating supplied message text alone needs no repository access.

## Establish the convention and input

Read repository instructions and contribution rules, then inspect recent
commits when a repository is available. Apply Clean Commit for an adopting
project or an explicit request, subject to repository requirements. Installing
the skill alone does not override an upstream project's commit convention.
If the user requests a Clean Commit example for comparison, keep it separate
from a commit that must follow another project's rules.

For staged changes, inspect `git status --short`, `git diff --cached --stat`,
and the actual `git diff --cached`, including relevant callers or surrounding
code when needed to understand the change. Distinguish unstaged and untracked
work from the staged diff; do not describe them as part of the commit. If the
index is empty, say so rather than invent a staged change or stage files.
For a supplied diff or message, use that input and disclose missing context.

## Subject format

```text
<emoji> <type>: <description>
<emoji> <type> (<scope>): <description>
<emoji> <type>!: <description>
<emoji> <type>! (<scope>): <description>
```

| Emoji | Type | Use |
| --- | --- | --- |
| 📦 | `new` | New features, capabilities, or dependencies |
| 🔧 | `update` | Existing-code changes, refactoring, performance, ordinary bug fixes |
| 🗑️ | `remove` | Remove code, features, or dependencies |
| 🔒 | `security` | Security fixes and vulnerability remediation |
| ⚙️ | `setup` | Initial configuration, CI, build systems, or tooling |
| ☕ | `chore` | Maintenance, dependency updates, or housekeeping |
| 🧪 | `test` | Test additions and test fixes |
| 📖 | `docs` | Documentation, guides, or comments |
| 🚀 | `release` | Version releases or release preparation |

Use the exact emoji and lowercase type. Prefer the specific purpose of the
change: adding a test is `test`, not `new`; a security fix is `security`, not
an ordinary `update`; new configuration is `setup`; ongoing dependency
maintenance is `chore`. Do not introduce a `fix` or `feat` type.

The description starts lowercase, uses present tense, has no final period,
and accurately describes the diff. The **entire subject**, including emoji,
type, optional scope, spaces, and punctuation, must be at most 72 characters.
Count the complete subject instead of estimating from the description alone.

Use one space between emoji and type, before an optional scope, and after the
colon. A scope is lowercase, preferably one word, and hyphenated when useful.
Omit it when it adds no clarity. Use one primary type; if the staged work is
unrelated, recommend splitting it without modifying the index unless asked.

## Breaking changes

Put a single `!` immediately after `new`, `update`, `remove`, or `security`,
before the optional scope or colon. It is invalid on `setup`, `chore`, `test`,
`docs`, or `release`. Choose the type from the actual change, then add `!`
only for a demonstrated compatibility break. Do not infer a break from size.

Prefer a `BREAKING CHANGE:` body explaining the incompatibility and migration
when using `!`. The specification also accepts a subject marker alone and a
body-only `BREAKING CHANGE:` for backward compatibility; do not reject those
forms or invent missing migration details.

```text
🔧 update! (api): return paginated results

BREAKING CHANGE: callers must read items from the results field.
```

## Draft, validate, or commit

- **Draft:** Return a usable message based on the requested diff. Briefly flag
  mixed changes or unknowns that materially affect it. Do not stage, commit,
  amend, or push during a draft-only request.
- **Validate:** Check format, exact emoji/type pairing, scope spacing, breaking
  marker eligibility, length, tense, punctuation, and fit to the supplied
  change. Explain concrete violations and give a corrected message when the
  evidence permits. Format validity alone does not prove semantic accuracy.
- **Commit:** When committing is authorized, recheck the index and selected
  files immediately before committing. Preserve unrelated work, follow
  repository-required checks, and pass the message as literal data. For a
  multiline body, use a message file rather than shell interpolation. Inspect
  the resulting commit and remaining status afterward. Amend, history rewrite,
  push, and release operations require their own scope in the user's request.

Reuse authorization already given; do not add a confirmation step to an
already-authorized ordinary commit. Never bypass a failed required check or
claim a commit succeeded without verifying it.

## Source and maintenance

Derived from [Clean Commit specification v1.1.0](https://github.com/wgtechlabs/clean-commit/blob/main/SPECIFICATION.md).
The mandatory format rules govern over inconsistent illustrative examples.
The essential rules are bundled here for independent installed use. This
repository owns the skill; update it alongside specification changes. Clean
Workflow can consume released copies downstream.
