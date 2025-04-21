
```markdown
# 🚀 Git Essentials: Branch vs Tag, Stash, Restore Guide

---

## 🔁 Branch vs 🏷️ Tag – Key Differences

| Feature            | 🌿 Branch                                      | 🏷️ Tag                                     |
|--------------------|------------------------------------------------|---------------------------------------------|
| 🔄 Mutable?        | ✅ Yes                                         | ❌ No (Immutable)                          |
| 📦 Purpose         | For development and ongoing updates            | For marking a specific release version      |
| 🌱 Creation        | From any branch                                | Usually from `master`                       |
| 📋 List Command    | `git branch`                                   | `git tag`                                   |
| ✍️ Create Command  | `git branch <branch-name>`                     | `git tag <tag-name>`                        |
| 🚀 Push Command    | `git push <alias> <branch-name>`               | `git push <alias> <tag-name>`               |
| 📤 Push All        | `git push <alias> --all`                       | `git push <alias> --tags`                   |
| ❌ Delete Command  | `git branch -d <branch-name>`                  | `git tag -d <tag-name>`                     |
| 📦 Downloadable    | No                                             | Yes (`.zip`, `.tar.gz` format)              |

---

## 🧪 Example: Tag Creation Workflow

```bash
# ✅ Step 1: List existing tags
git tag

# 🏷️ Step 2: Create a tag from master
git tag Airtel_V1.0.0  # Format: Major.Minor.Patch

# 🔍 Step 3: Verify
git tag

# ☁️ Step 4: Push to remote
git push airtel Airtel_V1.0.0
```

📌 **Note:** Tags appear in GitHub releases as downloadable `.zip` or `.tar.gz` archives.

---

## ❓ How to Create a Tag on GitHub (Remote Repo)

1. 🔧 Navigate to **Releases** tab.
2. ➕ Click **"Create new release"**.
3. 🏷️ Specify tag name (e.g., `v2.0.1`).
4. 📜 Add description and publish.

---

## 💾 Git Stash – Save Work in Progress

> Temporary shelf for uncommitted changes to switch branches safely.

### 🎯 Use Case

> You're working on a new feature in `dev`, and suddenly need to switch to `master` to fix a bug.

---

### 🧰 Git Stash Commands

```bash
# 📦 Save current changes with a name
git stash save "💻 Login feature WIP"

# 📜 See list of stashes
git stash list      # stash@{0}, stash@{1}, ...

# 🔁 Apply a specific stash
git stash apply stash@{1}

# 🗑️ Drop the most recent stash
git stash drop

# 🗑️ Drop a specific stash
git stash drop stash@{5}

# ⚡ Apply and delete in one go
git stash pop

# ❌ Delete all stash entries
git stash clear
```

🎯 **Pro Tip:** Use `git stash show -p stash@{n}` to preview contents before applying.

---

## ♻️ Restore Working Area Changes

Sometimes, we need to undo modifications in the working directory.

```bash
# Revert changes in a specific file
git restore <filename>
```

✅ **Note:** This resets the file to the last committed state.  
🧼 Useful for undoing accidental edits.

---
```
