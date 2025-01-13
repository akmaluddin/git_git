# Making and reasoning with changes

Now lets make changes, run the shell script

```bash
sh ./commands/change.sh
```

Lets see the changes that occur in our branch

```bash
git status
```

From this values, we can see the changes we are making, what their statuses are

Lets say we want to only stage changes to a specific file, how should we do that

```bash
git add *.txt
```

We run git status and oops, we have added a few to staged, lets remove that then. We need to find which ones we should not include that contains the line "this is wrong"

this is where `git diff` can be handy

Identify and "unstage" the file

<details>
<summary>How should I do that?</summary>
Depending on which state the files are, if its staged simply run

```bash
git restore --staged {filename/pattern}
```

The command `git reset` is also permissable to use, but the command overlaps and its best to create clear distinction

</details>

Now lets run git status, it appears that our file has now been unstaged but the changes are still in our working directory.

We would like to sync the changes back to our current branch state.

<details>
<summary>Is it the same command?</summary>
It uses a similar command but with a different flag since its no longer staged

```bash
git restore {filename/pattern}
```

</details>

It seems like we need to remove all the changes we made, how should we do that?

<details>
<summary>There is an untracked file</summary>
This is where clean can be handy

```bash
git clean -fdn
```

</details>
