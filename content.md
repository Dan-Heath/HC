# What is the difference between push, fetch, and pull?

[Git](https://git-scm.com/) provides several commands that let you synchronize your remote and local branches:

- `git push` - Uploads changes from a local branch to a remote repository
- `git fetch` - Downloads changes from a remote repository to your tracking branch
- `git pull` - Fetches and then merges changes into a local branch

Often `git push` and `git pull` are described as equivalent. This isn't entirely correct, since `git pull` does two things. 

The `git push` command lets you share code with a remote repository; it updates the remote branch so that it is identical to your local branch. The command checks for the tracking branch of a remote repository that is connected to your local branch. If there is a tracking branch, the command uploads any updates from the local branch to the remote branch. If the remote branch contains commits that are not in the local branch, the `git push` command fails because the branches are divergent. To resolve the failure, you must synchronize the local branch with the remote branch using either `git fetch` and `git merge` or `git pull`.

The `git fetch` command compares your local branch to a remote branch. If it finds changes in the remote branch, it downloads them from the remote branch to the local tracking branch. The `git fetch` command does not change your local branch. If you want to update your local branch with the changes from the remote branch, you also must run `git merge`.

The `git pull` command performs a `git fetch`, followed immediately by a `git merge`. It downloads any changes from the remote branch to the local tracking branch, and then merges them into your local branch. This command updates the local branch so that it is identical to the remote branch. The end result is usually what people want to do to keep their branches synchronized, however, some people prefer to use `git fetch` followed by `git merge` to preview the changes before they merge them.
