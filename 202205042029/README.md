# Git: Special Workflows

## Move Recent Commits to a New Branch
Accidentally making commits on mainline but then later realize you want to move
them to a feature branch. Ideally, you would want to transform the tree from
something like this:

```
mainline     A - B - C - D - E
```

To something like this:
```

newbranch         C - D - E
                 /
mainline    A - B
```

Follow this procedure:
```
# Note: Any changes not committed will be lost.
git branch newbranch        # Create a new branch, saving the desired commits
git checkout mainline       # checkout mainline, this is the place you want to go back
git reset --hard HEAD~N     # Move mainline back by N commits. This will destroy these commits non-reversibly on mainline 
git checkout newbranch      # Go to the new branch that still has the desired commits
```

For the guide full guide on how this is done, check it out [here](https://stackoverflow.com/questions/1628563/move-the-most-recent-commits-to-a-new-branch-with-git).


## Doing a Diff in Terminal
The build in `git diff` command is actually a really good way to check out how
changes happen in git.

Here are three really common uses for it
* When you want to see how the current state of your repository looks compared
to the head, use `git diff HEAD`
* When you want to see how the current state of your repository looks compared
to a given commit, use `git diff <commit SHA>`
* When you want to see the differences between two commits, you can use
`git diff <start commit SHA>..<end commit SHA>`

Like anything else, you can redirect the output to a file for easier viewing.


## Related
[202112140549](../202112140549) - Git: Helpful Commands

## Tags
#git
