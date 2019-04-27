Here are some common tasks in git/github

### Starting the day. Where was I? What was I doing?
```
git branch         # What branch am I currently on? e.g. {my_branch}
git status         # anything I forgot to commit? If so...
git commit ...     # Commit work in progress
```

### Didn't I do some work at home last night?
```
git checkout master       # leave whatever branch I was on
git fetch origin --prune  # Check for something new
git merge origin/master   # If updates available, update!
```

### Anything fun happening upstream?

```
git checkout master
git fetch upstream --prune  # grab latest changes from upstream repo
git merge upstream/master   # merge them into local copy of my form
git push origin master      # push latest upstream changes to my forked repo
git branch --merged master # check for any merged branches that can be safely deleted
git branch -d {name_of_merged_branch} # delete any fully merged branches
```

Now that `master` is up to date, you should merge whatever happened in `master` into your development branch:
```
git checkout {my_branch}
git merge master               # merges master->{my_branch}
git push origin {my_branch}    # Let Github know about the merge
```

## (Github) Life Rules
1. Always work on a branch: `git checkout -b my_branch_name`
2. Never push to `master`. Always work on a branch and do a pull request.
3. Seriously, don't do work on `master`. 
4. If you pushed it **anywhere**, don't `git rebase`. In fact, if you're reading this, don't `git rebase`.
