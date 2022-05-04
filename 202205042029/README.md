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


## Related
[202112140549](../202112140549) - Git: Helpful Commands

## Tags
#git
