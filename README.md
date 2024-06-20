# VSCode-Playground

A random internal tutorial that will be removed in the near future.

Taking the simplest approach in order to simplify the deploy to Azure.

## VSCode Virtual Environment

Using [Python environments in VS Code](https://code.visualstudio.com/docs/python/environments)

## Using pip and requirements.txt.

Be sure you have the virtual environment selected.

From the VS Code bash shell:

1. Install your current requirements.txt into the virtual environment.

```bash
pip install -r requirements.txt
```

1. Rename the requirements.txt file to something temporary.

Create a new requirements.txt. This new file has version numbers.

```bash
pip freeze >requirements.txt
```

### Internals

- Run `'ls -la` in your project directory.
- The `.venv` directory has your virtual directory.
- You can `cd` into it and look around.
- `cd` to `.venv/lib/python3.XXX/site-packages` to see your installed packages.
    (Replace XXX with your Python version)

## Useful Git Commands

```bash
# Initial repository checkout.
git clone <<repository name -- Under Code on the GitHub page>>

# Get latest repository changes.
git pull

# Add changed files, this will NOT add new files, only existing repository files that have changed.
git add -u

# Add new files. You can also add entire directories of files.
git add <<filename or directory>>

# See what is staged for commit.
git status

# Commit changes with a short comment. Leave off the -m if you want to leave a detailed commit comment.
git commit -m "My Comment"

# Mark a specific version. Useful for deploying a specific version to production.
git tag 0.1.1

# List all tags.
git tag

# Push local changes to the GitHub repository.
git push
```
