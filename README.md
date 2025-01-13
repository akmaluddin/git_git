# Branching

Well you made it to switch to this branch. If you used `switch` than thats wonderful

`checkout` is the old way and the reason why its less prefferred is the ambiguity however as long you manage then that is completely fine!

<details>
<summary>I want to know more</summary>
Two new commands "git switch" and "git restore" are introduced to split "checking out a branch to work on advancing its history" and
   "checking out paths out of the index and/or a tree-ish to work on
   advancing the current history" out of the single "git checkout"
   command.
   </details>

Lets take a look at all the branches we have in the repository

<details>
<summary>How do we do that?</summary>
To view the remote branches

```bash
git branch -r
```

To view local branches only

```bash
git branch
```

To view all branches

```bash
git branch -a
```

</details>

Lets create a branch from this

```bash
git switch -c your_branch_name
```

You have now moved over to a new branch, and your git history will be based on which ever branch you have branched from

You will observe your terminal will indicate as such with something along the lines of

```bash
branch 'test' set up to track 'origin/01-branching'.
Switched to a new branch 'test'
```

however... sometimes we are in a separate branch and would like to create a branch from another branch

to do so...

```bash
git switch -c your_branch_name starting_point
```

Now we are in a branch of our own, we can create a commit ourselves. For this excercise we are going to commit an empty change

```bash
git commit -m "hello" --allow-empty
```
