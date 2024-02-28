# Git commands

This cheatsheet provides a quick reference for common Git commands and workflows.

### Configuration

```bash
git config --global user.name "Your Name"
git config --global user.email "youremail@example.com"
git config --global color.ui auto
git config -l   # List current configurations 
```

### Setting Up a New Project

```bash
git init .   # Initialize a new Git repository in the current directory
```
**Note*: Do not delete the .git folder as it contains the repository's metadata.

### Create a new repository on the command line
```bash
echo "# git-commands" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/swapnilhpatil/git-commands.git
git push -u origin main
```
### Push an existing repository from the command line
```bash
git remote add origin https://github.com/swapnilhpatil/git-commands.git
git branch -M main
git push -u origin main
```


### Managing Files
```bash
touch index.html index.js main.css   # Create new files
git status                           # View status including untracked files and changes to be committed
git add filename                     # Stage changes for commit
git rm --cached filename             # Unstage changes
git add .                            # Stage changes recursively from the current directory downwards
git rm -r --cached .
```

### Committing Changes
```bash
git commit -m "Commit message"    # Commit staged changes with a message
git log                            # View commit history
git show <commit-hash>             # View detailed information about a specific commit
git diff                           # Show changes between commits
git restore filename               # Restore file to its state at the last commit
git commit --amend -m "New message"  # Amend the last commit with a new message
```

### Remote Repository Interaction
```bash
git remote add origin <repository-url>  # Add a remote repository
git branch                               # List local branches
git branch -M main                       # Rename the default branch to 'main'
git push -u origin main                  # Push changes to the remote 'main' branch
git push                                 # Push changes to the default remote branch
git pull                                 # Fetch and merge changes from the remote repository
```

### Branch Management
```bash
git branch       # List local branches
git branch -r    # List remote branches
git branch -a    # List all branches (local and remote)
git branch <branch-name>    # Create a new branch
git checkout <branch-name>  # Switch to a different branch
git checkout -              # Switch to the previously checked out branch
git checkout -b <branch-name>  # Create a new branch and switch to it
git branch -d <branch-name>    # Delete a branch
git merge <branch-name>        # Merge changes from another branch into the current branch
```

### General Workflow
```bash
git pull origin main   # Pull changes from the remote 'main' branch
git branch feature-a   # Create a new branch for feature development
git commit -m "Message"    # Commit changes to the feature branch
```

# Git Rebase Commands and Explanations

Git rebase is a powerful tool used to integrate changes from one branch onto another. It is commonly used to maintain a clean, linear project history. Here are some essential Git rebase commands along with explanations:

### git rebase

```bash
git rebase <branch-name>
```

**Explanation**: This command applies the changes in the current branch onto another branch. It moves the entire feature branch to begin on the tip of the <branch-name> branch, effectively incorporating changes from the other branch into the current branch.
### git rebase --continue
```bash
git rebase --continue
```
**Explanation**: After resolving conflicts during a rebase, this command allows you to continue the rebase process. It tells Git to proceed with the rebase operation once you have resolved any conflicts that occurred during the rebase.
### git rebase --abort
```bash
git rebase --abort
```

**Explanation**: This command aborts the current rebase operation and resets the branch to its state before the rebase began. It's useful if you encounter conflicts or other issues during the rebase process and want to start over.
### git rebase -i
```bash
git rebase -i <commit-hash>
```
**Explanation**: The interactive rebase command allows you to interactively rebase commits. It opens an editor where you can choose which commits to pick, squash, edit, or drop. It's useful for cleaning up commit history, combining commits, or rearranging commits before pushing to a shared repository.
### git rebase --onto
```bash
git rebase --onto <new-base> <old-base>
```

**Explanation**: This command allows you to move a series of commits from one branch to another. It's useful for rewriting history, such as moving a feature branch onto a different base branch, or for extracting changes from one branch to another.
### git pull --rebase
```bash
git pull --rebase
```
**Explanation**: When pulling changes from a remote repository, using git pull --rebase instead of git pull will rebase your local commits on top of the upstream branch, rather than merging the remote changes into your local branch. It helps maintain a cleaner commit history.
### git push --force-with-lease
```bash
git push --force-with-lease
```
**Explanation**: When you need to push changes after rebasing commits or making changes to the commit history, git push --force-with-lease allows you to force push changes to the remote repository without overwriting changes that others may have made. It's safer than git push --force.

### Additional Resources
- [GitHub Markdown Guide]
- [Git Guides]


## License

**MIT**

[GitHub Markdown Guide]: <https://docs.github.com/en/github/writing-on-github/basic-writing-and-formatting-syntax>
[Git Guides]: <https://github.com/git-guides/>
