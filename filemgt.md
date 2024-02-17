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
