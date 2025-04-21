

```markdown
# ✅ Git Best Practices

---

## 🔒 Commit Etiquette

- ❌ **Don't commit half-done work.**
- ✅ **Commit only when code is ready and tested.**
- 🧪 **Test thoroughly before committing.**
- 📝 **Use meaningful commit messages:**
  - Format: `"JIRA_ID: change message"`
  - Example: `165: updated pom.xml`

---

## 🔧 Collaboration Tips

- 🤝 **Coordinate with team to avoid merge conflicts.**
- 🚫 **Avoid blind merges – always raise Pull Requests.**
- 👀 **Monitor branches regularly.** Remove unused branches with proper approvals.
- 🧹 **Clean up stashes if not needed.**
- 📌 **Do not push directly to master/main. Use PR and code review process.**

---

# ⬇️ Git Clone Command

The `git clone` command is used to create a copy of an existing repository.

### 🧭 Steps:

1. 📁 Create a folder on Desktop.
2. 🔍 Navigate into the folder.
3. ⬇️ `git clone <repo-url>` – brings code + config.
4. 🌱 Create a staging branch and start working.

💡 **Note:** Default alias is `origin`  
📡 Check remotes using `git remote -v`

---

# 🔀 Git Merging Strategies

## ⚡ 1. Fast-Forward Merge

```text
Before:
A --- B --- C (master)
         \
          D --- E (feature)

After:
A --- B --- C --- D --- E (master)
```

✔ Happens when `master` hasn't changed since `feature` branched off.

---

## 🔁 2. Recursive Merge (Three-Way Merge)

```text
Before:
A --- B --- C (master)
         \
          D --- E (feature)

After:
A --- B --- C --------- M (master)
         \           /
          D --- E -- (feature)
```

✔ Used when both branches have commits since the split. Creates a merge commit `M`.

---

## 🔄 3. Merge vs Rebase

### 🔀 Merge (with merge commit)

Preserves history and shows when branches were combined.

### 📜 Rebase (linear history)

```text
Before:
A --- B --- C (master)
         \
          X --- Y --- Z (feature)

After Rebase:
A --- B --- C --- X' --- Y' --- Z' (feature)
```

✔ Rewrites commit history for a cleaner linear flow.

---

# 🍒 Git Cherry-pick

✅ Pick and apply specific commits from one branch to another:

```bash
git cherry-pick <commit-id>
```

---

# ⬇️ Git Pull vs Git Fetch

## 📥 Git Fetch

- Downloads data from remote repo into local.
- Manual merge needed afterward.

```bash
git fetch origin test
git merge origin/test
```

## 🔄 Git Pull

- `git fetch + git merge` combined.

```bash
git pull origin test
```

---

# ✏️ Edit Recent Commit Message

```bash
git commit --amend -m "New commit message"
# or
git commit --amend  # Opens editor
git push --force    # Updates commit on remote
```

---

# 🔐 Secure Your Repo

- 🛑 Avoid committing secrets, passwords, or API keys.
- ✅ Use `.gitignore` to prevent sensitive files from being tracked.

```bash
# Example .gitignore entries
node_modules/
.env
*.log
dist/
__pycache__/
```

🌐 Use [gitignore.io](https://www.toptal.com/developers/gitignore) for templates.

---

# 🔍 Useful Git Commands (Cheat Sheet)

- 🧱 View commit graph:
  ```bash
  git log --oneline --graph --all
  ```

- 📊 Show commit stats:
  ```bash
  git log --stat
  ```

- 🧑‍🔧 Who changed what in a file:
  ```bash
  git blame <filename>
  ```

- 🚫 Unstage a file:
  ```bash
  git reset <file>
  ```

- 🔁 Discard local file changes:
  ```bash
  git restore <file>
  ```

- 🧹 Clear all stashes:
  ```bash
  git stash clear
  ```

---

# 💡 Bonus Tips

- 🎯 Keep your branches focused – 1 task = 1 branch.
- 📘 Always write a meaningful PR description.
- 📅 Rebase before pushing if the base branch has changed.
- 👀 Review your changes using `git diff` before staging or committing.

---
