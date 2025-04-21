

```markdown
# 🌱 Git Branching & Merging - Complete Guide

## 🧭 Environments & Branch Roles

| Branch Name     | Purpose             | Notes |
|------------------|----------------------|-------|
| `dev`            | 🛠 Development         | For active feature building |
| `stg`            | 🧪 QA / Staging        | Used for testing before production |
| `master`         | 🚀 Production (Default) | Stable production-ready code |
| `release`        | 📦 Release Candidate   | Pre-production final staging |
| `feature/*`      | 🧩 Feature Development | Individual features or tasks |

⚠️ **Important:**  
- `master` is usually protected — 🔐 avoid direct pushes.  
- Use **Pull Requests (PRs)** to merge into `master` or `release`.

---

## 🌿 Git Branch Operations

### 📋 List all branches (local only)
```bash
git branch
```

### 🌍 List remote branches
```bash
git branch -r
```

### 🌐 List all branches (local + remote)
```bash
git branch -a
```

### 🌱 Create a new branch
```bash
git branch <branch-name>
```

### 🔁 Switch to a different branch
```bash
git checkout <branch-name>
```

### 🚀 Create & switch to a new branch
```bash
git checkout -b <branch-name>
```

🧠 **Pro Tip:** Branch names should be short, meaningful, and use hyphens like:
```
feature/add-login
bugfix/header-crash
hotfix/security-patch
```

---

## 🔀 Git Merging Explained

### ✅ Steps for Merging a Branch

1. **Switch to base branch** (e.g., `master`):
   ```bash
   git checkout master
   ```

2. **Compare branches:**
   ```bash
   git diff development
   ```

3. **Merge the target branch:**
   ```bash
   git merge development
   ```

---

## ⚔️ Merge Conflicts

### 🔧 Resolving Conflicts - Steps

1. Attempt merge:
   ```bash
   git merge development
   ```

2. Git shows a conflict — fix manually:
   - Open file
   - Remove conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`)

3. Stage and commit:
   ```bash
   git add .
   git commit -m "Resolved merge conflicts"
   ```

---

## 🌍 Remote Operations

### 🔼 Push branch to remote
```bash
git push origin <branch-name>
```

### 📤 Push all branches
```bash
git push origin --all
```

### 🔄 Pull latest changes from remote
```bash
git pull origin <branch-name>
```

### ❌ Delete a remote branch
```bash
git push origin :<branch-name>
```

---

## 🏷️ Renaming & Deleting Branches

### ✏️ Rename a branch
```bash
git branch -m <old-name> <new-name>
```

### 🗑️ Delete a local branch
```bash
git branch -d <branch-name>
```
⚠️ You can’t delete the branch you’re currently on.

---

## 🧪 Feature Branch Workflow

```bash
git checkout -b feature/user-auth       # Create feature branch
# Make changes, then:
git add .
git commit -m "Add user auth module"
git push origin feature/user-auth       # Push to remote
```

Open a pull request to merge into `dev` or `release`.

---

## ✅ Good Practices

- Use PRs for merging into `master`/`release`.
- Frequently merge small changes.
- Protect critical branches like `master`.
- Use `.gitignore` to skip unnecessary files.
- Keep commit messages clear and relevant.

---

## 🛠 Bonus: Git Aliases

```bash
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.cm commit
git config --global alias.st status
git config --global alias.last "log -1 HEAD"
```

Run like:
```bash
git co dev
git br
git cm -m "Add footer UI"
```
```

