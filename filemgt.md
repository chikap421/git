# Git File Management Guide

Git is a powerful tool for version control, allowing you to track changes, collaborate on projects, and more. Here's how to manage files effectively within a Git repository.

## Deleting Files

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
## Renaming Files
To rename or move a file and track the change:

```bash
git mv old/path/to/file new/path/to/file
git commit -m "Rename file"
git push
```
This command stages the move (or rename) and commits it in one step.

## Ignoring Files
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

## Handling Line Endings

Consistent line endings are crucial for collaboration across different operating systems. Configure Git to automatically handle line endings:

- **On Windows**
  ```bash
  git config --global core.autocrlf true

- **On macOS and Linux**

```bash
git config --global core.autocrlf input
```

This setup ensures that Git automatically converts CRLF line endings into LF when you add a file to the repository, maintaining consistency.
