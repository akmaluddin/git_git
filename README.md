# Getting changes in

Collaborative works means we need to take changes from others

You should be a bit familiar with `git pull`

> [!TIP]
> Sometimes your branch and the remote may have diverged
> Then you might need to perform a fast forward with either rebase or merge strategy

Your colleague has made some modifications on another branch and while you were working on your branch you needed to pull them in

Lets pull in the changes made in your colleagues branch. There are two ways in reconciling the history

1. Merge

```bash
git fetch
git merge origin/SUB-03-colleague-changes
```

2. Rebase

```bash
git fetch
git rebase origin/SUB-03-colleague-changes
```

Take your time to familiarise with the two options. But how do we restore our merge or rebase?

```bash
git reset --merge ORIG_HEAD
```
