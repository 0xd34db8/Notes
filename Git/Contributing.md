Opening an issue first depends almost entirely on the scope of the change.

In open source, the general etiquette breaks down into three distinct tiers:

### 1. The "Issue First" Tier (Architecture, New Features, Refactors)

* Always open an issue first if you are:
* Adding a new feature or command-line flag.
* Refactoring existing architecture or changing internal patterns.
* Changing public API contracts or user-facing behavior.


* **Why:** Maintainers carry the burden of long-term maintenance. If a feature does not align with the project roadmap, they will reject it—meaning hours of your work will go straight into the trash.
* **The Pitch:** Briefly explain the problem you are solving, your proposed design, and ask: *"Is this something you’d accept a PR for, and does this approach sound right to you?"*

### 2. The "Direct PR" Tier (Bug Fixes, Typos, Minor Polish)

* You generally do **not** need an issue first for:
* Clear bug fixes with an obvious reproduction and an accompanying regression test.
* Documentation fixes, dead link repairs, or typo corrections.
* Dependency security bumps or trivial compiler/linter warnings.


* **Why:** For trivial or indisputable fixes, opening an issue just adds administrative noise to the maintainer's notification queue. The PR *is* the discussion.

### 3. The "Look for Existing Work" Tier (Community Etiquette)

Before typing any code or opening a ticket:

* **Check the `CONTRIBUTING.md`:** Many large repos explicitly state: *"We do not accept unsolicited PRs without an approved issue"* or *"Please claim an issue before starting work."* Always defer to their explicit rules.
* **Search open issues and PRs:** Ensure three other contributors haven't already opened PRs attempting to solve the exact same edge case.
* **Ask to be assigned:** If you find an existing open issue labeled `help wanted` or `good first issue`, leave a quick comment: *"I'd like to work on this, mind assigning it to me?"* This prevents duplicated effort.

---

### How to Structure the PR When You Do Open It

When you are ready to open the pull request:

* **Link the context:** Use GitHub's closing keywords in the description (e.g., `Closes #123` or `Fixes #456`).
* **Keep scope atomic:** Fix one thing per PR. Bundling a bug fix with a formatting cleanup across 20 files makes review miserable and drastically slows down merging.
* **Provide before/after evidence:** If there is visual or behavioral change, include screenshots, CLI logs, or terminal outputs.
* **Respect maintainer bandwidth:** Maintainers are often volunteers. Don't `@mention` them 12 hours after submitting; give them a week or two before gently checking in.
