# Contributing to Clean Commit

Thank you for your interest in contributing to Clean Commit! We welcome contributions from everyone.

---

## Table of Contents

- [How to Contribute](#how-to-contribute)
- [Proposing Changes to the Workflow](#proposing-changes-to-the-workflow)
- [Improving Documentation](#improving-documentation)
- [Discussion Guidelines](#discussion-guidelines)
- [Code of Conduct](#code-of-conduct)

---

## How to Contribute

There are many ways to contribute to Clean Commit:

### 1. **Use It and Share Feedback**
   - Try Clean Commit in your projects
   - Share your experience with the community
   - Report what works and what doesn't

### 2. **Improve Documentation**
   - Fix typos or unclear explanations
   - Add more examples
   - Improve existing examples
   - Translate documentation

### 3. **Propose Enhancements**
   - Suggest improvements to the specification
   - Propose new examples or use cases
   - Share edge cases we haven't covered

### 4. **Participate in Discussions**
   - Help answer questions from other users
   - Share your expertise and insights
   - Engage in specification discussions

---

## Proposing Changes to the Workflow

The Clean Commit workflow is intentionally minimal and stable. Changes to the core specification require careful consideration.

### Before Proposing a Change

Ask yourself:
- Does this change make the workflow simpler or more complex?
- Is this solving a real problem that many users face?
- Can existing types handle this use case?
- Does this maintain the "Clean Code deserves Clean Commit" philosophy?

### How to Propose a Change

1. **Open an Issue**
   - Use the "Specification Change Proposal" template (if available)
   - Clearly describe the problem you're trying to solve
   - Explain why existing types don't work
   - Provide real-world examples

2. **Include These Details**
   - **Problem:** What issue are you addressing?
   - **Current Behavior:** How does Clean Commit handle this now?
   - **Proposed Solution:** What change are you suggesting?
   - **Examples:** Show before/after examples
   - **Impact:** How does this affect existing users?

3. **Be Open to Discussion**
   - The community will review and discuss your proposal
   - Be prepared to iterate on your idea
   - Consider alternative solutions
   - Accept that not all proposals will be accepted

### Types of Changes

**Minor Changes** (easier to accept):
- Clarifications to existing documentation
- Additional examples
- Improved explanations
- Edge case guidelines

**Major Changes** (require strong justification):
- Adding new commit types
- Changing type definitions
- Modifying format rules
- Removing existing types

---

## Improving Documentation

Documentation improvements are always welcome!

### What to Improve

- **Clarity:** Make explanations easier to understand
- **Examples:** Add more real-world examples
- **Organization:** Improve structure and navigation
- **Completeness:** Fill gaps in documentation
- **Accuracy:** Fix errors or outdated information

### How to Contribute Documentation

1. **Fork the Repository**
   - Fork the repository on GitHub: https://github.com/wgtechlabs/clean-commit
   - Clone your fork:
   ```bash
   git clone https://github.com/YOUR-USERNAME/clean-commit.git
   cd clean-commit
   ```

2. **Create a Branch**
   ```bash
   git checkout -b docs/improve-examples
   ```

3. **Make Your Changes**
   - Edit the relevant markdown files
   - Follow existing formatting conventions
   - Keep language simple and friendly

4. **Use Clean Commit Workflow**
   ```bash
   📖 docs: improve examples in quick reference
   📖 docs (readme): add missing installation step
   📖 docs: fix typo in specification
   ```

   **Automate with GitHub Copilot (Optional):**
   
   Configure VS Code to auto-generate Clean Commit messages:
   
   ```json
   {
     "github.copilot.chat.commitMessageGeneration.instructions": [
       {
         "text": "Use Clean Commit workflow: <emoji> <type>: <description> or <emoji> <type> (<scope>): <description>. Choose type: 📦 new=user-facing features/functionality, 🔧 update=modify existing code/logic, 🗑️ remove=delete code/features, 🔒 security=fix vulnerabilities, ⚙️ setup=configs/CI/tooling/.github files, ☕ chore=maintenance/deps/LICENSE, 🧪 test=test files, 📖 docs=README/guides/comments, 🚀 release=version tags. Format: lowercase type, present tense (add not added), no period, max 72 chars. Examples: ⚙️ setup: add GitHub funding configuration | 📦 new: user authentication | 🔧 update (api): improve error handling | ☕ chore (deps): bump react version"
       }
     ]
   }
   ```

5. **Submit a Pull Request**
   - Describe what you changed and why
   - Link to any related issues
   - Request review from maintainers

---

## Discussion Guidelines

When participating in discussions:

### Do:
- ✅ Be respectful and constructive
- ✅ Focus on ideas, not people
- ✅ Provide concrete examples
- ✅ Listen to different perspectives
- ✅ Assume good intentions
- ✅ Stay on topic

### Don't:
- ❌ Be dismissive or condescending
- ❌ Make personal attacks
- ❌ Derail conversations
- ❌ Spam or promote unrelated content
- ❌ Argue in bad faith

### Healthy Discussion Example

> "I think we should consider adding a 'fix' type because bug fixes are common. However, I see how 'update' already covers this. Maybe we could clarify in the docs that bug fixes should use 'update'?"

### Unhealthy Discussion Example

> "This workflow is useless without a 'fix' type. Anyone who thinks otherwise doesn't understand real development."

---

## Code of Conduct

### Our Pledge

We are committed to providing a welcoming and inclusive environment for everyone, regardless of:
- Experience level
- Background
- Identity
- Personal characteristics

### Expected Behavior

- Use welcoming and inclusive language
- Respect differing viewpoints and experiences
- Accept constructive criticism gracefully
- Focus on what's best for the community
- Show empathy towards other community members

### Unacceptable Behavior

- Harassment or discriminatory language
- Trolling or insulting comments
- Personal or political attacks
- Publishing others' private information
- Any conduct inappropriate in a professional setting

### Enforcement

Violations of the code of conduct may result in:
1. Warning from maintainers
2. Temporary ban from discussions
3. Permanent ban from the project

Report violations to the project maintainers.

---

## Review Process

### For Documentation Changes

1. **Submission:** Submit your pull request
2. **Review:** Maintainers review within 7 days
3. **Feedback:** Address any requested changes
4. **Approval:** Once approved, changes are merged
5. **Credit:** You'll be credited in the contributors list

### For Specification Changes

1. **Discussion:** Open issue for community discussion
2. **Consensus:** Allow time for community input (minimum 2 weeks)
3. **Decision:** Maintainers evaluate based on feedback
4. **Implementation:** If approved, update documentation
5. **Announcement:** Communicate changes to users

---

## Questions?

- **General Questions:** Open a GitHub Discussion
- **Bug Reports:** Open a GitHub Issue
- **Security Issues:** Contact maintainers directly

---

## Recognition

All contributors will be recognized in our documentation. Thank you for helping make Clean Commit better!

---

## License

By contributing to Clean Commit, you agree that your contributions will be licensed under the MIT License.

---

<p align="center">
  <strong>Thank you for contributing to Clean Commit!</strong>
</p>
