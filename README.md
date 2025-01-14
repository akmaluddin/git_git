# Traversing history

We have taken a look at the history of our changes, but sometimes its also needed to traverse and move within the history

There are a few ways to do so:-

1. Walking back

```bash
git switch -d HEAD~1
```

2. Finding a specific sha

```bash
git switch -d {sha}
```

While this is wonderful, we now dont have a way to move back to where we started. How do we get back

1. This is where you can move back to the branch itself.

```bash
git switch {branch}
```

2. Walk forwards (or backwards whichever way you see it)

```bash
git reflog
```

```bash
git switch -d HEAD@{1}
```

## Now I am proposing a different method altogether

Most of the time when walking between histories you want to actually keep your current tip and the other history as separate files / folders
This is usefull for comparisons and moving between code

utilising worktrees

```bash
git worktree add {folder-name e.g. temp} {sha or HEAD~1}
```

Now you should see that you have another folder inside your working directory and you could `cd` into it and treat it as a separate entitiy

This makes it far more safer when touching history stuff and you have two snapshots for your use case

Whats also wonderful is since there is distinction, you could make changes safely and create a branch to where it was diverged

```bash
git switch -c {name-of-branch}
```

to clean up the worktree run

```bash
git worktree remove {folder-name}
```

## Linear history or not linear history
