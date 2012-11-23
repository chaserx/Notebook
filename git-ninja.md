# So you've nuked the branch from CI

Here's a way to make an empty commit and rollback

    git commit --allow-empty

    git rebase -i HEAD^^

    git push -f
