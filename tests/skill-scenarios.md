# Clean Commit skill verification

These are repeatable manual checks, not a claim that an agent evaluation has
passed. Run them before releasing skill changes and record actual outcomes.
Use disposable local repositories with no push destination.

## Installation

1. In a test Codex environment without Clean Workflow, add this checkout as a
   local marketplace: `codex plugin marketplace add /absolute/path/to/clean-commit`.
2. Run `codex plugin add clean-commit@clean-commit`, then
   `codex plugin list --marketplace clean-commit --json`. Confirm installation.
3. Start a fresh chat and ask `$clean-commit validate this message: 📦 new: add search`.
   Confirm discovery and that the skill works without another Clean skill.
4. Load only `skills/clean-commit/` in another Agent Skills-compatible host and
   repeat the request. No resource outside that folder should be required.
5. For remote installation, repeat with `wgtechlabs/clean-commit --ref BRANCH_OR_TAG`
   as the marketplace source. Verify the installed source matches the tested ref.
6. Remove only the test installation and marketplace afterward.

## Behavior

Record prompts, initial index/status/HEAD, responses, and final index/status/HEAD.
Drafting and validation must leave all three unchanged.

| Request or setup | Expected observable result |
| --- | --- |
| Draft from a staged ordinary bug fix and unstaged new feature | Message describes only the fix using `🔧 update`; the unstaged feature is excluded |
| Draft from an empty index | Reports no staged changes; does not stage files or fabricate a commit |
| Draft from unrelated staged feature and docs edits | Recommends splitting logical changes without changing the index |
| Validate `📦 new: add search` and `🔧 update (api): fix pagination` | Accepts both format forms |
| Validate `📦 new(api): add search` and `🔧 update: Fix pagination.` | Identifies scope spacing, capitalization, and final-period violations |
| Validate `🔧 update! (api): change response shape` and `⚙️ setup!: add ci` | Accepts the eligible breaking marker and rejects `!` on setup |
| Validate a body-only `BREAKING CHANGE:` or eligible subject-only `!` | Recognizes both supported forms; recommends body detail without inventing it |
| Validate complete subjects of exactly 72 and 73 characters | Accepts the length of the first and rejects the second, counting prefix and scope too |
| Repo requires Conventional Commits; draft for its staged change | Follows the repository rule without migrating its convention |
| Commit a specifically staged change with commit authorization | Rechecks the index, runs required checks, commits only intended work, and verifies the resulting commit; no push or amend |

Exercise all nine type choices with matching changes: new capability (`new`),
ordinary fix (`update`), feature deletion (`remove`), vulnerability fix
(`security`), initial CI configuration (`setup`), dependency update (`chore`),
test-only change (`test`), guide-only change (`docs`), and release preparation
(`release`). Check exact emoji/type pairing against `SPECIFICATION.md`.

To produce deterministic length inputs, run:

```sh
python3 - <<'PY'
prefix = '📖 docs: '
for length in (72, 73):
    subject = prefix + 'a' * (length - len(prefix))
    print(length, subject)
PY
```

Package discovery and static inspection do not prove these behavioral checks.
