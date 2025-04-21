🧠 Git Interview Questions & Answers
🔄 Difference between git add . and git add *

Command	Description
git add .	Adds all files (new, modified) recursively in the current directory and subdirectories.
git add *	Adds only non-hidden files in the current directory (not recursive). Ignores files starting with a dot .
📌 Note: git add * does not include .gitignore, .env, etc.

🧹 How to remove files from the working area?
bash
Copy
Edit
git clean -n   # 🔍 Preview the files to be deleted
git clean -f   # ❌ Forcefully deletes the untracked files
⚠️ Note: Only new (untracked) files are deleted. Modified files are kept.

🔁 Is it possible to move files from staging area to working area?
bash
Copy
Edit
git reset               # 🔄 Moves all files from staging to working area
git reset <filename>    # 🎯 Moves a specific file from staging to working area
❌ Revert a Bad Commit (Application is not working)
bash
Copy
Edit
git revert <commit-id>
🔙 Reverts changes made by a specific commit.
📌 Note: This creates a new commit that undoes the previous changes. It does not affect the remote repo immediately.

🧼 How to delete an updated code from remote repo?
Delete or modify the unwanted files locally.

Then push your changes:

bash
Copy
Edit
git push origin master
🔁 This syncs the local repo with the remote, effectively removing the undesired updates.

🆚 Difference Between git reset and git revert

Command	Action
git reset	Moves files from staging ➡️ working area (unstages changes)
git revert	Creates a new commit that undoes changes from a previous commit
🚫 What is a .gitignore file?
🗂️ The .gitignore file tells Git which files or folders not to track.

📄 Example:

plaintext
Copy
Edit
node_modules/
.env
*.log
✅ Use it to avoid pushing sensitive or unnecessary files into your repository.
