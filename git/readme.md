
# Git & GitHub Cheat Sheet

## 1. Initial Git Setup

### Set global user identity

```bash
git config --global user.name "Your Name"
git config --global user.email yourname@example.com
```

### Set default branch to `main`

```bash
git config --global init.defaultBranch main
```

### View global configuration

```bash
git config --list
```

### Get current Git user info

```bash
git config --get user.name
git config --get user.email
```

---

## 2. Repository Initialization

### Initialize a new repository

```bash
git init
```

### Clone an existing repository

```bash
git clone https://github.com/username/repo.git
```

---

## 3. Basic Workflow

### Check repository status

```bash
git status
```

### Track a file

```bash
git add filename
```

### Track all files

```bash
git add .
```

### Commit changes

```bash
git commit -m "Commit message"
```

### Add and commit in one command

```bash
git commit -am "Commit message"
```

(Works only for already tracked files)

---

## 4. Branching

### List branches

```bash
git branch
```

### Create a new branch

```bash
git branch branch-name
```

### Switch branch

```bash
git checkout branch-name
```

### Create and switch branch

```bash
git checkout -b branch-name
```

### Rename current branch

```bash
git branch -m new-branch-name
```

### Delete a branch

```bash
git branch -d branch-name
```

---

## 5. Remote Repositories (GitHub)

### Add remote origin

```bash
git remote add origin https://github.com/username/repo.git
```

### View remotes

```bash
git remote -v
```

### Push to GitHub (first time)

```bash
git push -u origin main
```

### Push changes

```bash
git push
```

### Pull latest changes

```bash
git pull
```

---

## 6. Viewing History

### View commit history

```bash
git log
```

### Compact log view

```bash
git log --oneline
```

### View changes in a file

```bash
git diff
```

---

## 7. Undo & Fix

### Unstage a file

```bash
git restore --staged filename
```

### Discard local changes

```bash
git restore filename
```

### Amend last commit

```bash
git commit --amend
```

### Reset to previous commit (soft)

```bash
git reset --soft HEAD~1
```

### Reset to previous commit (hard)

```bash
git reset --hard HEAD~1
```

---

## 8. Stashing

### Save work temporarily

```bash
git stash
```

### List stashes

```bash
git stash list
```

### Apply stash

```bash
git stash apply
```

### Apply and remove stash

```bash
git stash pop
```

---

## 9. Tags

### Create a tag

```bash
git tag v1.0.0
```

### Push tags

```bash
git push --tags
```

---

## 10. GitHub Authentication

### Set remote using SSH

```bash
git remote set-url origin git@github.com:username/repo.git
```

### Check SSH connection

```bash
ssh -T git@github.com
```

---

## 11. Useful Shortcuts

### Show ignored files

```bash
git status --ignored
```

### Clean untracked files

```bash
git clean -fd
```

### Show current branch

```bash
git branch --show-current
```

