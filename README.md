# Advanced use case

Sometimes you want to also traverse file changes that happen in a point in history

This can be useful to undo some changes you have made in your current branch but not tracked in the remote

In order to do so sometimes its useful to view changes that occur per file

<details>
<summary>How to view history per file?</summary>
To do so use `git log`

```bash
git log --oneline -- {filename}
```

Or simply...

```bash
git log --oneline {filename}
```

</details>

<details>
<summary>How to view all the changes made to file</summary>

```bash
git log -p -- {filename}
```

</details>

Once able to identify the SHA you would like to restore the file from, we can then reuse the trusty `git restore` command again

```bash
git restore --source {SHA here} {filename}
```
