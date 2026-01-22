
# GIT CHEAT SHEET

##  INITIAL SETUP

```sh
git config --global user.name "Your Name"       # set global username
git config --global user.email yourname@example.com  # set global email
git config --global init.defaultBranch main    # default branch main
git config --list                              # view global config
git config --get user.name                     # get username
git config --get user.email                    # get email
```

---

## REPOSITORY INIT

```sh
git init                                      # initialize repo
git clone https://github.com/username/repo.git  # clone repo
```

---

##  BASIC WORKFLOW

```sh
git status                                    # check repo status
git add filename                              # track a file
git add .                                     # track all files
git commit -m "message"                       # commit changes
git commit -am "message"                      # add & commit tracked files
```

---

##  BRANCHING

```sh
git branch                                    # list branches
git branch branch-name                         # create branch
git checkout branch-name                       # switch branch
git checkout -b branch-name                    # create & switch
git branch -m new-branch-name                  # rename current branch
git branch -d branch-name                      # delete branch
```

---

##  REMOTE REPOSITORIES

```sh
git remote add origin https://github.com/username/repo.git  # add remote
git remote -v                                   # view remotes
git push -u origin main                          # first push
git push                                        # push changes
git pull                                        # pull latest
```

---

##  VIEW HISTORY

```sh
git log                                        # commit history
git log --oneline                               # compact log
git diff                                       # show changes
```

---

##  UNDO & FIX

```sh
git restore --staged filename                  # unstage file
git restore filename                           # discard local changes
git commit --amend                             # amend last commit
git reset --soft HEAD~1                         # soft reset previous commit
git reset --hard HEAD~1                         # hard reset previous commit
```

---

## STASHING

```sh
git stash                                      # save work temporarily
git stash list                                 # list stashes
git stash apply                                # apply stash
git stash pop                                  # apply & remove stash
```

---

## TAGS

```sh
git tag v1.0.0                                # create tag
git push --tags                                # push tags
```

---

##  GITHUB AUTHENTICATION

```sh
git remote set-url origin git@github.com:username/repo.git  # switch to SSH
ssh -T git@github.com                               # check SSH connection
```

---

##  USEFUL SHORTCUTS

```sh
git status --ignored                             # show ignored files
git clean -fd                                    # remove untracked files/dirs
git branch --show-current                        # show current branch
```

## git removed .env from all history commit 
First run 
```git
git filter-branch --force --index-filter "git rm --cached --ignore-unmatch .env" --prune-empty --tag-name-filter cat -- --all
```
clean github backup ref
```git
Remove-Item -Recurse -Force .git\refs\original
git reflog expire --expire=now --all
git gc --prune=now --aggressive
```


