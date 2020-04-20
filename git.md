# GIT CheatSheet

### Clone Repo
```
git clone git://sub.domain.com/repo.git

    # only one branch
    git clone -b mybranch --single-branch git://sub.domain.com/repo.git
```

### Checkouts
```
git checkout mybranch

## checkout files from a branch
git checkout <branch_name> -- <paths>
```

### Fetch
```
git fetch origin -v --prune
```

### Merge
```
git merge --no-stat -v origin/mybranch
```

### PUSH
```
git push -v origin
  ## or just a branch
  git push -v origin mybranch
```

## Branches

### Show branches
```
git branch -a
```

### Delete branch
```
git branch -d mybranch
```

### Rename a branch (locally and remote)
```
git branch -m old_branch new_branch         # Rename branch locally
git push origin :old_branch                 # Delete the old branch
git push -u origin new_branch   # Push the new branch, set local branch to track the new remote
```

### Remove info from deleted branches on origin
```
git remote prune origin
    ## or (you can also set as a default)
    git fetch --prune
```

### Delete all branches but master
```
git branch | grep -v master | xargs git branch -D
```

### Create branch BEST WAY after git fetch (and clean branch)
```
    git checkout -b mybranch
# Push new branch to origin (.gitconfig >> [push] default = current)
    git push -u origin branch/name
```

### Create branch from origin/XXXXX
```
git checkout -b mybranch origin/mybranch
```

### ULTRA CLEAN
```
git checkout -- .
```

### Remove untracked files from your bran (-n to list them)
```
git clean -f -n
```

### RESET Branch
```
git fetch --all
git reset --hard origin/master
```

### Revert to a commit
```
git reset --hard COMMIT_HASH
git push -f
```

### Change upstream
```
git branch branch_name --set-upstream-to your_new_remote/branch_name
```

### git log of file
```
git log -p filename
git log --all --decorate --oneline --graph
```

### Rebase
```
git checkout your-branch
git fetch origin master:master
git rebase master
git push -f

  #now your changes will enter clean at the top
  git checkout master
  git merge your-branch
```

### Commits
```
# to keep 1 commit per PR (trunk base development) use amend to keep ading to the last commit
git commit --amend --no-edit
```

### Log
```
git log --oneline
```

