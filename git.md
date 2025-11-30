🚀 FULL GIT COMMAND LIST (MASTER CHEAT SHEET)
🟦 1. CONFIGURATION
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
git config --global core.editor "code --wait"
git config --list

🟩 2. REPOSITORIES
Initialize
git init

Clone
git clone <url>
git clone <url> <folder-name>

🟨 3. STAGING & COMMITTING
git status
git add <file>
git add .
git reset <file>
git commit -m "message"
git commit -am "add + commit skipped staging"
git commit --amend

🟧 4. BRANCHING
git branch
git branch <name>
git branch -d <name>          # delete merged branch
git branch -D <name>          # force delete
git checkout <name>
git checkout -b <name>
git switch <name>
git switch -c <name>

🟥 5. MERGING
git merge <branch>
git merge --abort

🟪 6. DIFF (COMPARING CHANGES)
git diff                      # unstaged
git diff --cached             # staged
git diff HEAD                 # working vs last commit
git diff <file>
git diff <commit1> <commit2>
git diff <branch1> <branch2>
git diff --name-only
git diff --stat

🟦 7. LOG & HISTORY
git log
git log --oneline
git log --graph --oneline --decorate
git show                      # show last commit
git show <commit>

🟫 8. RESET / RESTORE / REVERT (UNDO!)
Undo staged file
git reset <file>

Undo last commit (keep changes)
git reset --soft HEAD~1

Undo last commit (remove changes)
git reset --hard HEAD~1

Restore a file to last commit
git restore <file>

Undo a commit safely
git revert <commit>

🟩 9. STASHING (SAVE WORK TEMPORARILY)
git stash
git stash save "message"
git stash list
git stash show
git stash show -p
git stash apply
git stash pop
git stash drop
git stash clear

🟦 10. REMOTES (GitHub)

(Ignore if you're only doing local)

Add remote
git remote add origin <url>

Remove remote
git remote remove origin

Show remotes
git remote -v

Push
git push
git push -u origin main
git push origin <branch>

Pull
git pull
git pull origin main

Fetch
git fetch
git fetch --all

🟨 11. TAGGING
git tag
git tag v1.0
git tag -a v1.0 -m "release"
git show v1.0
git tag -d v1.0

🟫 12. CLEANING
git clean -n     # preview what will be removed
git clean -f     # remove untracked files
git clean -fd    # remove untracked files + folders

🔥 13. ADVANCED BUT USEFUL
Reset a branch to remote state
git reset --hard origin/main

Cherry-pick a commit
git cherry-pick <commit>

Rename a branch
git branch -m <new-name>

⭐ THE 15 COMMANDS YOU MUST KNOW FOR CLASS
git init
git clone <url>
git status
git add .
git commit -m "msg"
git log --oneline
git branch
git checkout -b test
git merge test
git diff
git diff --cached
git stash
git reset --hard
git push
git pull
