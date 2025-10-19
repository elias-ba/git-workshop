# Git & GitHub Cheatsheet

## Configuration (First Time Setup)

```bash
# Set your identity
git config --global user.name "Your Name"
git config --global user.email "your@email.com"

# Check your settings
git config --list

# Set default branch name to 'main'
git config --global init.defaultBranch main

# Set default editor (optional)
git config --global core.editor "code --wait"  # For VS Code
```

## Creating & Initializing Repositories

```bash
# Create a new local repository
git init

# Clone an existing repository
git clone <repository-url>

# Clone into a specific folder
git clone <repository-url> <folder-name>
```

## Basic Snapshotting

```bash
# Check status of your files
git status

# Add file to staging area
git add <file>

# Add all files to staging area
git add .

# Add all files of a specific type
git add *.js

# Remove file from staging area (unstage)
git reset <file>

# Commit staged changes
git commit -m "Your commit message"

# Add and commit in one command
git commit -am "Your commit message"

# Amend the last commit (change message or add forgotten files)
git commit --amend -m "New commit message"
```

## Viewing History

```bash
# View commit history
git log

# View compact history (one line per commit)
git log --oneline

# View history with graph
git log --graph --oneline --all

# View last N commits
git log -n 5

# View changes in each commit
git log -p

# View commits by specific author
git log --author="Name"

# View commits in date range
git log --since="2 weeks ago" --until="yesterday"
```

## Viewing Changes

```bash
# Show unstaged changes
git diff

# Show staged changes
git diff --staged

# Show changes in a specific file
git diff <file>

# Show changes between commits
git diff <commit1> <commit2>
```

## Branching

```bash
# List all local branches
git branch

# List all branches (local and remote)
git branch -a

# Create a new branch
git branch <branch-name>

# Switch to a branch
git checkout <branch-name>

# Create and switch to a new branch
git checkout -b <branch-name>

# Switch to a branch (newer syntax)
git switch <branch-name>

# Create and switch to new branch (newer syntax)
git switch -c <branch-name>

# Delete a branch (safe - prevents deletion if unmerged)
git branch -d <branch-name>

# Force delete a branch
git branch -D <branch-name>

# Rename current branch
git branch -m <new-name>
```

## Merging

```bash
# Merge a branch into current branch
git merge <branch-name>

# Merge with no fast-forward (creates merge commit)
git merge --no-ff <branch-name>

# Abort a merge (if conflicts)
git merge --abort

# Continue merge after resolving conflicts
git merge --continue
```

## Working with Remotes

```bash
# List remote connections
git remote

# List remote connections with URLs
git remote -v

# Add a remote repository
git remote add origin <repository-url>

# Change remote URL
git remote set-url origin <new-url>

# Remove a remote
git remote remove <remote-name>

# Fetch changes from remote (doesn't merge)
git fetch origin

# Pull changes from remote (fetch + merge)
git pull origin <branch-name>

# Pull with rebase instead of merge
git pull --rebase origin <branch-name>

# Push to remote repository
git push origin <branch-name>

# Push and set upstream branch
git push -u origin <branch-name>

# Push all branches
git push --all origin

# Delete remote branch
git push origin --delete <branch-name>
```

## Undoing Changes

```bash
# Discard changes in working directory
git checkout -- <file>

# Restore file (newer syntax)
git restore <file>

# Unstage file but keep changes
git reset HEAD <file>

# Unstage file (newer syntax)
git restore --staged <file>

# Undo last commit but keep changes staged
git reset --soft HEAD~1

# Undo last commit and unstage changes
git reset HEAD~1

# Undo last commit and discard changes (DANGEROUS)
git reset --hard HEAD~1

# Revert a commit (creates new commit that undoes changes)
git revert <commit-hash>
```

## Stashing (Temporary Storage)

```bash
# Stash current changes
git stash

# Stash with a message
git stash save "Work in progress on feature X"

# List all stashes
git stash list

# Apply most recent stash
git stash apply

# Apply and remove most recent stash
git stash pop

# Apply specific stash
git stash apply stash@{2}

# Delete a stash
git stash drop stash@{0}

# Delete all stashes
git stash clear

# Show stash contents
git stash show -p
```

## Inspecting & Comparing

```bash
# Show commit details
git show <commit-hash>

# Show file at specific commit
git show <commit-hash>:<file>

# Compare branches
git diff <branch1>..<branch2>

# Show commits in branch1 not in branch2
git log <branch1> --not <branch2>

# Show who changed what in a file
git blame <file>
```

## Tagging

```bash
# List all tags
git tag

# Create lightweight tag
git tag <tag-name>

# Create annotated tag
git tag -a <tag-name> -m "Tag message"

# Tag specific commit
git tag <tag-name> <commit-hash>

# Push tag to remote
git push origin <tag-name>

# Push all tags
git push origin --tags

# Delete local tag
git tag -d <tag-name>

# Delete remote tag
git push origin --delete <tag-name>
```

## GitHub Collaboration

```bash
# Fork a repository (done on GitHub website)

# Clone your fork
git clone <your-fork-url>

# Add upstream remote (original repo)
git remote add upstream <original-repo-url>

# Fetch from upstream
git fetch upstream

# Merge upstream changes
git merge upstream/main

# Keep fork synced (fetch + merge)
git pull upstream main
```

## .gitignore

Create a `.gitignore` file to exclude files from version control:

```bash
# Ignore specific file
secrets.txt

# Ignore all files with extension
*.log

# Ignore folder
node_modules/
.env

# Ignore files in any directory
**/temp/

# Exception - don't ignore this file
!important.log
```

## Common Workflows

### Feature Branch Workflow

```bash
# Start new feature
git checkout -b feature/new-feature

# Work and commit
git add .
git commit -m "Add new feature"

# Push feature branch
git push -u origin feature/new-feature

# Create Pull Request on GitHub

# After PR approved, merge and delete branch
git checkout main
git pull origin main
git branch -d feature/new-feature
```

### Fixing Merge Conflicts

```bash
# When merge conflict occurs
git status  # See conflicted files

# Open conflicted files and resolve
# Look for <<<<<<, =======, >>>>>> markers
# Edit to keep desired changes

# After resolving
git add <resolved-files>
git commit -m "Resolve merge conflicts"
```

### Syncing Fork

```bash
# Fetch upstream changes
git fetch upstream

# Switch to main
git checkout main

# Merge upstream
git merge upstream/main

# Push to your fork
git push origin main
```

## Useful Aliases

Add these to your `~/.gitconfig` or use `git config --global alias.<name> <command>`:

```bash
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.st status
git config --global alias.unstage 'reset HEAD --'
git config --global alias.last 'log -1 HEAD'
git config --global alias.visual 'log --graph --oneline --all'
```

## Tips & Best Practices

1. **Commit often**: Make small, focused commits
2. **Write good commit messages**: Clear, descriptive messages
3. **Pull before push**: Always pull latest changes before pushing
4. **Use branches**: Never work directly on main
5. **Review before commit**: Use `git diff` to review changes
6. **Don't commit sensitive data**: Use `.gitignore` for secrets
7. **Keep commits atomic**: One logical change per commit

## Good Commit Message Format

```
Short summary (50 chars or less)

More detailed explanation if needed (wrap at 72 chars).
Explain the problem this commit solves and why you made
this change.

- Bullet points are okay
- Use present tense: "Add feature" not "Added feature"
```

## Emergency Commands

```bash
# Oh no, I committed to the wrong branch!
git checkout correct-branch
git cherry-pick <commit-hash>
git checkout wrong-branch
git reset --hard HEAD~1

# I need to undo my last push (DANGEROUS - only if no one else pulled)
git reset --hard HEAD~1
git push --force

# I accidentally deleted important changes
git reflog  # Find lost commits
git checkout <commit-hash>

# Discard all local changes and match remote
git fetch origin
git reset --hard origin/main
```

## Getting Help

```bash
# Get help for a command
git help <command>
git <command> --help

# Quick help
git <command> -h
```
