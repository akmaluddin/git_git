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

It seems like we only wanted to pull in certain changes of files from your colleagues branch and not the whole branch

<details>
<summary>Why would you ever need it?</summary>
Most of the time this is never needed, but lets say you depend on a feature developed by another branch and you would only want to incorporate those changes without bringing in other changes that could potentially be unstable
</details>

There are a few options:-

1. Cherry-pick

Identify the hash

```bash
git log --oneline origin/SUB-03-colleague-changes
```

cherry pick

```bash
git cherry-pick {hash}
```

<details>
<summary>You could take changes in a range</summary>
You can take changes within a range of commits. To do so identify the start and end range

```bash
git cherry-pick {start}...{end}
```

</details>

2. Restore

```bash
git restore --source origin/SUB-03-colleague-changes {file}
```

> [!NOTE]
> These two commands are not the same and not interchangeable. One takes commits and along with it takes all the changes in said commits
> aside to that it also takes in the commit and incorporate it into your git history
> The other takes in files and would take neither the commit changes and commit history
