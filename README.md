# Git Memo Commands:

### delete file:
```bash
git rm <file-name>
```
### remove specific file from git cache:
```bash
git rm --cached <file-name>
```

### remove all files from git cache:
```bash
git rm -r --cached .
git add .
git commit -m "gitignore cache updated"
```

### log:
```bash
git log
```

### move to specific commit:
```bash
git reset --hard <commit-hash> // rollback files to the state of a specific commit, pointer: <commit-hash>
```

### check current branch:
```bash
git branch
```

### remove current branch:
```bash
git branch -d [-r (remote)] <branch-name>
```

### rename current branch:
```bash
git checkout <old-branch-name>
git branch -m <old-branch-name> <new-branch-name>
```

### checkout to specific branch:
```bash
git checkout [-b (create)] <branch-name>
```

### merge branches:
```bash
git checkout <branch-name>
git merge <with-branch-name>
```

### check remote storages:
```bash
git remote -v
```

### get changes from remote repo:
```bash
git fetch
```

### git fetch + git merge:
```bash
git pull
```

### stash:
```bash
git stash                      - hide local changes
git stash apply stash@{0}@{0}  - return uncommited local changes (@{0} - name of stash item)
git stash apply                - return uncommited last local item
git stash list                 - show list of uncommited changes
git stash clear                - clear list of uncommited changes
```

### resolved this error by updating username and credentials:
```bash
git config user.name "user-name"        
git config credential.username "user-name"
git config user.email "user-email"
```

### push new branch to remote storage:
```bash
git push -u <origin> (name-of-remote-storage) <master> <name-of-local-branch>
```

### exclude .gitignore only local files:
```bash
.git/info/exclude (exclude .gitignore only local files (do not push changes to remote .gitignore file))
git update-index --assume-unchanged <file-name>
git update-index --no-assume-unchanged <file-name>
```

### remove a single file from the staging area for git:
```bash
git reset HEAD -- <file> OR <dir>
```

### delete your local branch:
```bash
git branch -d (-D) <branch-name>
```

### check ssh keys:
```bash
ls ~/.ssh
```

### find ssh keys (address):
```bash
find ~/.ssh
```

### ssh-key generate:
```bash
ssh-keygen -t ed25519 -C "<comment>"
```

### copy ssh key to clipboard:
```bash
pbcopy < ~/.ssh/id_ed25519.pub
```

### if you prefer subshells, you could try the following (though it is more fragile):
```bash
ssh-agent $(ssh-add /somewhere/yourkey; git clone git@github.com:user/project.git <folder name>)
example: ssh-agent $(ssh-add ~/.ssh/Vladimir988; git clone git@github.com:Vladimir988/Redux.git redux)
ssh-agent $(ssh-add ~/.ssh/id_ed25519; git remote add origin git@github.com:Vladimir988/Redux.git)
```

### check which user is via SSH:
```bash
ssh -T git@github.com
```

### determine which key was associated with your_current_github_username:
```bash
cat ~/.ssh/*.pub
```

### how to specify the username that SSH should send to the remote system using the git GUI:
```bash
eval "$(ssh-agent -s)" && ssh-add ~/.ssh/your_current_github_username       example: (eval "$(ssh-agent -s)" && ssh-add ~/.ssh/Vladimir988)
```

### check remote repository:
```bash
git remote -v
```

### delete remote repository from your local (origin as usual):
```bash
git remote remove <branch-name> - (origin as usual)
```

### find ssh keys (address):
```bash
git remote add <name-remote-ssh-hub> <ssh-link> (git@github.com:Vladimir988/Laravel-Ci-Cd.git)
```
