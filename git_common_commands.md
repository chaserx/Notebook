# Common Git Commands

## Rebasing local branch to remote branch

    git pull --rebase remote branch

example

    git pull --rebase origin master

## Forced Push

*WARNING*: need to adjust git config with the following line so that the push does not automatically force push all branches:

    git config --global push.default current

After a pull with the rebase option, often necessary to force the push back to the remote with:

    git push -f

## Git log

Show a pretty git history in the console with:

    git log --oneline --graph --decorate --all

## Git Untrack a file

    git rm --cached file
    git rm -r --cached folder