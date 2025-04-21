
# 🧠 Git Interview Q&A

## 🔄 Difference between `git add .` and `git add *`

| Command         | Description |
|----------------|-------------|
| `git add .`     | Adds **all** files (new, modified) recursively from the current directory including hidden files. |
| `git add *`     | Adds **only non-hidden** files in the current directory (not recursive). |

📌 **Note**: `git add *` skips files like `.env`, `.gitignore`, etc.



---

## 🧹 How to Remove Files from the Working Area?

```bash
git clean -n   # 🔍 Preview files to be deleted
git clean -f   # ❌ Delete untracked files
```

⚠️ **Note**: Only **untracked** (new) files are deleted. **Modified** files remain untouched.


---

## 🔁 Move Files from Staging Area to Working Directory

```bash
git reset               # 🔄 Moves all staged files back to working area
git reset <filename>    # 🎯 Moves specific file back to working area
```

---


## ❌ Revert a Bad Commit (App not working)

```bash
git revert <commit-id>
```


🧯 This creates a new commit that **undoes** the changes from the specified commit.  
📌 It does **not** affect the remote repo unless pushed.

---


## 🧼 Delete Updated Code in Remote Repo

> Scenario: You’ve already deleted the updated code locally. Now sync with the remote.

```bash
git push origin master
```


This will overwrite the remote changes with your local repo.

---

## 🆚 Difference Between `git reset` and `git revert`

| Command       | Description |
|---------------|-------------|
| `git reset`   | Moves files from staging ➡️ working area (unstages changes) |
| `git revert`  | Creates a **new commit** that reverts previous changes |

---


## 🚫 What is a `.gitignore` File?

The `.gitignore` file tells Git which files/folders **not to track**.

📄 **Example**:
```
node_modules/
.env
*.log
.DS_Store
```

✅ Helps avoid pushing unnecessary or sensitive files into the repository.

