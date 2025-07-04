# Prompting the use of submodules

## Initialize adding the submodules
`git submodule add {submodule repo name}`

## Before reviewing local code base, check for submodules
`git submodule status`

## Update the current local project with the latest remote submodules
Should be done whenever the local project has been refreshed or there have been changes performed in the submodules remotely directly.

`git submodule update --remote `

## If a remote agent needing to work on a remote repo with submodules
`git submodule update --init --recursive`

## The remote agent updates the submodules from within the parent project
### Navigate to the submodule
`cd path/to/submodule`

### Stage and commit your changes to the submodule
```
git add .
git commit -m "Fix bug in submodule functionality"
```

### Push the changes to the submodule's remote repository
`git push origin main`

### Go back to parent repo
`cd ../..`

### The parent repo now needs to reference this new commit
```
git add path/to/submodule
git commit -m "Update submodule reference after local changes"
git push origin main
```
