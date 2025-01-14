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

This is where you can move back to the branch itself.

```bash
git switch {branch}
```

Or you could utilise reflogs
