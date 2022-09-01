# What is the difference between push, fetch, and pull?

[Git](https://git-scm.com/) provides several commands that let you synchronize your remote and local branches:

- `git push` - Uploads changes from a local branch to a remote repository
- `git fetch` - Downloads changes from a remote repository to your tracking branch
- `git pull` - Fetches and then merges changes into a local branch

Often `git push` and `git pull` are described as equivalent. This isn't entirely correct, since `git pull` does two things. 

The `git push` command lets you share code with a remote repository; it updates the remote branch so that it is identical to your local branch. The command checks for the tracking branch of a remote repository that is connected to your local branch. If there is a tracking branch, the command uploads any updates from the local branch to the remote branch. If the remote branch contains commits that are not in the local branch, the `git push` command fails because the branches are divergent. To resolve the failure, you must synchronize the local branch with the remote branch using either `git fetch` and `git merge` or `git pull`.

The `git fetch` command compares your local branch to a remote branch. If it finds changes in the remote branch, it downloads them from the remote branch to the local tracking branch. The `git fetch` command does not change your local branch. If you want to update your local branch with the changes from the remote branch, you also must run `git merge`.

`git pull` simply does a `git fetch` followed immediately by `git merge`. This is often what we desire to do, but some people prefer to use `git fetch` followed by `git merge` to make sure they understand the changes they are merging into their branch before the merge happens.
