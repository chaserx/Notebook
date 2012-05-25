# Uncommon Git Commands

## Compare two branches

    git diff master..branch

    git log master..branch

## Show files that have changed between two branches

    git diff --name-status master..branch

## Similar to show files that have changed between branches but with more detail

    git diff --stat --color master..branchName

    git diff --stat --color branchName..master

## Branch renaming

    git branch -m <old name> <new name>


