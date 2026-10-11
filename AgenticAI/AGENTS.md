# Commit Message Syntax

**Standard Format:**
When generating commit messages for this repository, ALWAYS use the following plain-text format. Do NOT use markdown. Start with a lowercase commit type (e.g. `feat:`, `fix:`, `chore:`), followed by a brief description. Then, on the next lines, provide a bulleted list of specific changes using an indent and single hyphens (`- `).

Example:
```text
feat: improve package management and download UX
- Optimistic UI on Global Pkgs uninstall
- Display size of each package in global packages & the total size of all pacakges
- Show npm version sizes on the Version Manager page & Download page
```

# Commit Message Workflow

**Writing Commits to .gitmessage:**
When changes are substantial enough to warrant a commit, agents should generate the commit message and add it to the `.gitmessage` file.
- **Append, Do NOT Overwrite:** Always ADD (append) new commit messages. You must NEVER overwrite any previous text already present in `.gitmessage`.

# Release Process

When a new release is required, follow these steps:

1. **Read Commits:** Retrieve all commits since the last release tag (e.g., `git log <last_tag>..HEAD --oneline`).
2. **Write Release Notes:** Categorize the commits (e.g., Features, Bug Fixes, Maintenance, etc.) and write them in Markdown format (no emojis) into the `RELEASE_NOTES.md` file in the repository root.
3. **Commit Notes:** Commit the changes to `RELEASE_NOTES.md`.
4. **Tag Release:** Create a git tag with the new version number (e.g., `git tag v2.0.3`).
5. **Push:** Push the commit and the tag to GitHub (`git push origin main` and `git push origin vX.Y.Z`).

The GitHub Actions workflow `.github/workflows/release.yml` will automatically detect the new tag, build the app, read `RELEASE_NOTES.md` to populate the GitHub release body, and publish the release.
