# Add GitHub Remote

Whenever I make a new repo in GitHub, it doesn't give me the page with git commands on how to connect my local repo to the remote one. This is my notes on what I remember doing.

## Make a GitHub Repo

Make a GitHub repo. Then copy the SSH link.

## Make local a git repo

```bash
git init
```

## Connect the remote to the local

```bash
git remote add <ssh_that_was_copied>
```

### Check the remote

```bash
git remote -v
```

## Can't push to remote?

You might get an error message that you need to fetch from the remote first.

```bash
git pull --rebase origin main
```

### Merge conflicts

Most likely there are merge conflicts. If you're doing all of this in the Terminal and not using GitHub Desktop, then check the files listed in the Terminal that have merge conflicts.

**Hints:** Usually, the ones with merge conflicts would be the files that are in the remote repo like the `README.md` and `.gitignore`.

### After you've resolved the merge conflicts

```bash
git rebase --continue
...
git status
```
After `git status`, there should be have been a bunch of track and untracked files. 

### Track and commit
Do what you need to do with the files then 

```bash
git add .
git commit -m "Resolved merge conflicts."
git status
git rebase --continue
```

### Finally push!
```bash
git push
```
If that doesn't work then 
```bash
git push --set-upstream origin main
```
