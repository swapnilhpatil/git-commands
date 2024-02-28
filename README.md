# git-commands
Added all git commands

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
Note: Do not delete the .git folder as it contains the repository's metadata.

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
### Additional Resources


- [GitHub Markdown Guide]
- [Git Guides]

[GitHub Markdown Guide]: <https://docs.github.com/en/github/writing-on-github/basic-writing-and-formatting-syntax>
[Git Guides]: <https://github.com/git-guides/>

## License

MIT
