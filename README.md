# Gitty_life
git description for beginners


# 🧠 Introduction

Git is a version control tool that helps you track, share, and collaborate on code. GitHub is a platform to host Git repositories online.

This cheatsheet summarizes the **most useful commands**, their **meanings**, and **real-world examples** — especially for RStudio users.

---

# 📁 1. Git Setup

## Set your Git identity (so GitHub knows it’s you)

```bash
git config --global user.name "Ehsan Zangene"
git config --global user.email "zangeneh.ehsan@gmail.com"
```

💡 Your email **must be verified on GitHub** or your contributions won’t show up.

---

# 🔨 2. Initialize & Clone Repositories

## Create a Git repo in your current folder
```bash
git init
```

## Clone an existing repo from GitHub
```bash
git clone git@github.com:esnzgn/your-repo-name.git
```

💡 Use SSH for push access without typing your password each time.

---

# ✏️ 3. Making & Saving Changes

## Check repo status
```bash
git status
```

## Stage changes (prepare for commit)
```bash
git add filename.R
git add .          # Add all changes
```

## Commit changes (save a snapshot)
```bash
git commit -m "Add volcano plot for MTX-R comparison"
```

---

# 🌐 4. Push & Pull with GitHub

## Push local commits to GitHub
```bash
git push origin main
```

## Pull new commits from GitHub to your computer
```bash
git pull origin main
```

💡 Set default strategy for future pulls:
```bash
git config --global pull.rebase true   # Use rebase instead of merge
```

---

# 🌱 5. Branches & Merging

## Create and switch to a new branch
```bash
git checkout -b test-analysis
```

## Switch between branches
```bash
git checkout main
```

## Merge a branch into `main`
```bash
git checkout main
git merge test-analysis
```

---

# 🧪 6. Common Issues & Solutions

## 🔥 Error: Not a git repository

```bash
fatal: not a git repository
```
**Fix**: Make sure you’re inside a Git folder.

---

## ❗ Error: Local changes would be overwritten

```bash
git pull
# Error: your local changes would be overwritten
```

**Fix**:
```bash
git add .
git commit -m "WIP before pull"
git pull --rebase
```

---

## ❗ Error: Push rejected (non-fast-forward)

```bash
git pull --rebase
git push
```

---

## ❗ Wrong email in commits

Check:
```bash
git log --pretty=format:'%an <%ae>' | head
```

Fix:
```bash
git commit --amend --reset-author
git push --force
```

---

# 🧼 7. Undo & Clean

## Unstage a file
```bash
git reset filename.R
```

## Undo last commit (but keep changes)
```bash
git reset --soft HEAD~1
```

## Discard all local changes (⚠️ dangerous!)
```bash
git checkout -- .
```

---

# 📚 8. Forks vs Branches

| Concept | Description |
|--------|-------------|
| **Branch** | A parallel line of development within a repo |
| **Fork**   | A full copy of someone else’s GitHub repo (usually to contribute without access) |

---

# 👀 9. Viewing History

## See commit history
```bash
git log
git log --oneline --graph --decorate
```

## See file change history
```bash
git log filename.R
```

---

# 🧠 10. Git & RStudio

- Use RStudio’s Git tab for staging, committing, and pushing  
- Use Terminal for merging, rebasing, and resolving errors  
- Use `usethis::use_git()` and `usethis::use_github()` to initialize new Git projects

---

# ✅ Summary Table

| Task                | Command                          |
|---------------------|----------------------------------|
| Initialize repo     | `git init`                       |
| Clone repo          | `git clone URL`                  |
| Check status        | `git status`                     |
| Add changes         | `git add .`                      |
| Commit              | `git commit -m "Message"`        |
| Push                | `git push origin main`           |
| Pull                | `git pull --rebase`              |
| Create branch       | `git checkout -b name`           |
| Merge branch        | `git merge name`                 |
| Fix author identity | `git commit --amend --reset-author` |

---

# 🙌 Final Note

Use Git **early** and **often**. It's not just for collaboration — it's the best way to protect your code and stay sane.

---

*Created by Ehsan Zangene – because Git gets confusing fast.*