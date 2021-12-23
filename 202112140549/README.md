# Git: Helpful Commands

|   Command                          |   Use
|   -                                |   -
|   git checkout -b branch_name      | Create a new branch and checkout
|   git branch -M master main        | Rename branch master to main
|   git branch -D branch_name        | Force delete the local branch (do after GH PR and merge)
|   git branch -a                    | Show all the local and remote branches
|   git pull --prune origin          | Remove remote branch (after it is deleted on GH)
|   git log [--oneline]              | Show your log of Git commits, --oneline is a shorthand log
|   git checkout commit_id           | Go back to specific commit
|   git switch -c <new_branch>       | When you go back to an old commit and want to create a new branch from that point
|   git merge branch_to_merge        | Merge the specified branch into your currrent branch


## Tags
#git
