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

1. Create a new requirements.txt. This new file has version numbers.

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

# Push local tags to GitHub repository. Must always be done separately from the push.
git push --tags

```

### Working With Branches

1. When working on changes it is prudent to create a new branch.
This allows you to check in work in progress without changing your known-good code.

    ```bash
    # Create a new branch and switch to it.
    git switch -c <<branch name>>

    # List available branches. "main" is your known-good code.
    git branch
    ```

2. Make changes and commit them to the branch.

1. Test your changes.

1. If everything looks good, switch back to the main branch and merge the changes.

    ```bash
    git switch main
    git merge <<branch name>>
    ```

1. You can now delete the merged branch.

    ```bash
    git branch -d <<branch name>>
    ```

### Forgetting Changes

It's not unusual to be working on a change and come to the conclusion that you've wandered down the wrong path and need to start over.

```bash
# Forget changes before you `git add` them.
git restore <<filename>>

# Forget changes after you `git add` them but before you commit them.
git restore --staged <<filename>>

# Forget everything you've done on this branch and go back to the known-good code.
# Think carefully before doing this one.
git switch main
git branch -D <<branch name>>
