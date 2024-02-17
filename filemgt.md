# Git File Management Guide :book:

Git is a powerful tool for version control, allowing you to track changes, collaborate on projects, and more. Here's how to manage files effectively within a Git repository.

## Deleting Files :wastebasket:

To remove a file from both your repository and local filesystem:

```bash
git rm path/to/file
git commit -m "Remove file"
git push
```
To delete a file from the repository but keep it locally:

```bash
git rm --cached path/to/file
git commit -m "Stop tracking file"
git push
```
## Renaming Files :pencil2:
To rename or move a file and track the change:

```bash
git mv old/path/to/file new/path/to/file
git commit -m "Rename file"
git push
```
This command stages the move (or rename) and commits it in one step.

## Ignoring Files :see_no_evil:
To prevent certain files or patterns from being tracked:

1. Create a .gitignore file in your repository's root.
2. Add file patterns to ignore.

```bash
# Ignore all txt files
*.txt
# Ignore a specific file
path/to/myfile.log
# Ignore all files in a specific directory
path/to/directory/*
```
3. Commit the `.gitignore` file
```bash
git add .gitignore
git commit -m "Add gitignore"
git push
```

## Handling Line Endings :twisted_rightwards_arrows:

Consistent line endings are crucial for collaboration across different operating systems. Configure Git to automatically handle line endings:

- **On Windows**
  ```bash
  git config --global core.autocrlf true

- **On macOS and Linux**

```bash
git config --global core.autocrlf input
```

This setup ensures that Git automatically converts CRLF line endings into LF when you add a file to the repository, maintaining consistency.

## Viewing File Changes :mag:
To see what changes have been made:

```bash
git diff  # Shows unstaged changes
git diff --staged  # Shows changes staged for commit
```

## Reverting Changes :back:
To undo changes in a specific file"

```bash
git checkout -- path/to/file  # Reverts unstaged changes
```
To revert a committed change:

```bash
git revert commit_id  # Creates a new commit that undoes the changes
```
To find a `commit_id` for use with commands like `git revert`, you can use the `git log` command, which displays a log of commits for the repository. Here's how:



## Finding a Specific Commit ID :mag_right:
### Viewing Commit History
1. **Open your terminal** and navigate to your Git repository directory.
2. **Run the `git log` command**:
```bash
git log
```
This command shows a list of recent commits, including the commit ID (SHA-1 hash), author, date, and commit message.
- The output of `git log` will look something like this:
``` sql
commit 1a2b3c4d5e6f7g8h9i0j (HEAD -> main, origin/main)
Author: Your Name <you@example.com>
Date:   Thu Sep 7 12:34:56 2021 -0400

    Your commit message here
```
- In this case, the string **`1a2b3c4d5e6f7g8h9i0j`** is the commit ID. 
### Simplifying the Git Log Output
- If you want a simpler view of the commit log, you can use:
``` bash
git log --oneline
```
This command condenses each commit to a single line, showing a short commit ID and the commit message.
### Using the Commit ID
- Once you've identified the `commit_id` you want to revert or interact with, you can use it in various Git commands, like:
```bash
git revert 1a2b3c4d5e
```
- This example reverts the changes introduced by the specified commit. Git will create a new commit that undoes the changes made by **`1a2b3c4d5e`**.
### Note
- The `commit_id` is typically a 40-character SHA-1 hash, but you only need to use enough characters to uniquely identify the commit in your repository. Generally, the first 6-10 characters are sufficient.
- Managing files effectively in Git ensures a clean and traceable development history. Always commit related changes together and write meaningful commit messages.
