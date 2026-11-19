# **Contribute to someone's repo**

## **Fork → Clone → Branch → Code → Push → PR**

You work on your fork, not directly on the original repository.

### **1. Fork the repository**

Go to the original repo:

Original repo

[vaaibhavmishra/viclip](https://github.com/vaaibhavmishra/viclip?utm_source=chatgpt.com)

Click **Fork** → create your own copy under your GitHub account.

Your fork will look like:

`your-username/viclip`

### **2. Clone your fork locally**

```
git clone https://github.com/your-username/viclip.git
cd viclip
```

### **3. Add the original repo as upstream**

This lets you fetch updates from the original repository.

```
git remote add upstream https://github.com/vaaibhavmishra/viclip.git
```

Check your remotes:

```
git remote -v
```

You should have:

- `origin` → your fork
- `upstream` → original repo

### **4. Create a feature branch**

Don't work directly on `main`. Create a separate branch for each feature or fix.

```
git checkout -b feat/your-feature-name
```

Examples:

```
git checkout -b feat/add-dark-mode
git checkout -b fix/navbar-responsive
git checkout -b feat/add-user-settings
```

### **5. Make your changes**

Implement your feature, test it, and review the changes.

```
git status
git diff
```

Commit your work:

```
git add .
git commit -m "feat: add your feature"
```

### **6. Push your branch to your fork**

```
git push -u origin feat/your-feature-name
```

This pushes your feature branch to **your GitHub fork**, not the original repo.

### **7. Raise a Pull Request (PR)**

On GitHub:

1. Open your fork.
2. Click **Compare & pull request**.
3. Make sure the PR targets the **original repository**, not your fork.
4. Verify the branch comparison:
   - **Base repository:** `vaaibhavmishra/viclip`
   - **Base branch:** `main` (or whatever branch the project uses)
   - **Head repository:** `your-username/viclip`
   - **Compare branch:** `feat/your-feature-name`
5. Write a clear title and description.
6. Click **Create pull request**.

The maintainer reviews your code, requests changes if necessary, and eventually merges or rejects it.&#x20;

[image](https://www.google.com/s2/favicons?domain=https://docs.github.com\&sz=32)



## **The exact Git workflow**

```

# Clone your fork
git clone https://github.com/your-username/viclip.git
cd viclip

# Add original repository as upstream
git remote add upstream https://github.com/vaaibhavmishra/viclip.git

# Create feature branch
git checkout -b feat/my-feature

# Make changes, then stage and commit
git add .
git commit -m "feat: add my feature"

# Push branch to your fork
git push -u origin feat/my-feature

```

Then create the PR on GitHub.

## **One thing experienced contributors also do**

Before starting work, sync your fork with the original repo so you're not working on outdated code.

```
git checkout main
git fetch upstream
git merge upstream/main
git push origin main
```

Then create your feature branch from the updated `main`.

Also, **check the repo's README, issues, and contribution guidelines before coding**. For a new feature, it's generally smarter to open an issue or discuss the idea first—especially if the project is actively maintained—to avoid spending time building something the maintainers don't want.

[image](https://www.google.com/s2/favicons?domain=https://docs.github.com\&sz=32)

# Issues

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
