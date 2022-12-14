# Git commands cheatsheet
## Best practices
When creating a fork, the remote name for the fork is `origin` and the remote name for the original repository is `upstream`.
```
> git remote -v
origin	git@github.com:TammieYu/tammie-code-help.git (fetch)
origin	git@github.com:TammieYu/tammie-code-help.git (push)
upstream	git@github.com:dzhengg/tammie-code-help.git (fetch)
upstream	git@github.com:dzhengg/tammie-code-help.git (push)
```

Always create a branch specifically for your feature, and make your changes in that branch. Do not make changes directly in the `main` or `develop` branches.

Multiple smaller commits are better than one giant commit. Each commit should contain changes that serve a single purpose. E.g. for a set of changes to support addition in a calculator app, it is better to have:
```
commit3: Support addition for any amount of numbers
commit2: Support addition of 2 numbers
commit1: Support parsing + signs in math expressions
```
instead of:
```
commit1: Support addition operation
```
## Daily use
Check whether your files have been staged or committed
```
git status
```

Create a new branch called `<branch name>`
```
git checkout -b <branch name>
```

Add specific files to be in `staged` status
```
git add <file1> <file2>
```

Add all files to be in `staged` status
```
git add -A
```

Add only modified files (not new files) to be `staged` status
```
git add -u
```

Remove specific files from `staged` status
```
git restore --staged <file1> <file2>
```

Remove all files from `staged` status
```
git restore --staged .
```

Commit files in `staged` status
```
git commit
```

Delete a branch called `<branch name>`
```
git branch -d <branch name>
```

### Working with forks
Update your local `develop` branch with any changes to the upstream `develop` branch
```
git checkout develop
git pull upstream develop
```

Updating your local `tammie-feature` feature branch with the latest changes to the upstream `develop` branch.
```
git checkout tammie-feature
git merge develop
```

Push your local `tammie-feature` feature branch to your fork. Once this is done, you can go to the upstream repository and create a pull request. The base repository and branch will be the upstream repository and the branch that you want to make changes to (e.g. git@github.com:dzhengg/tammie-code-help.git and develop). The head repository and branch will be your fork and your feature branch (e.g. git@github.com:TammieYu/tammie-code-help.git and tammie-feature)
```
git push origin tammie-feature
```

## Useful links
* [Git cheatsheet](https://education.github.com/git-cheat-sheet-education.pdf)
