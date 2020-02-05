# GIT

Created by Vince Chang </br>

Here is where I post useful information on how to use GIT


GIT:
[GIT REPO w/ Notes](https://github.com/nnja/advanced-git)


#### NOTES
- Set up a text editor to open if you don’t pass -m in commit
```
git.io/config-editor
git config --global core.editor atom —wait
git config --global core.editor sublime -n -w
```

#### 3 Areas of Where Code Lives
1. Working Area
  1. The files that are also not in your staging area, not handled by git
  2. Also called “untracked files”
2. Staging Area
  1. Aka the index or cache
  2. This is how git knows what will change between the current commit and the next commit
3. Repository
  1. All the files git knows about
  2. Contains all the commits


#### Moving files in and out of the Staging Area
```
git add <file>
git rm <file>
git mv <file>
```

#### Git stash
- Save uncommitted work
- The stash is safe from destructive operations
- Git stash = stash changes
- Git stash list = list changes
- Git stash show@{0} = show the contents
- Git stash apply = apply the last stash
- Git stash apply stash@{0} = apply a specific stash
- Git stash —include-untracked = keep untracked files
- Git stash —all = keep all files (even ignored ones)
- Git stash pop = remove the last stash and apply the changes


#### Branch
- Is a pointer to a particular commit
- The pointer of the current branch changes as new commits are made

#### Head
- HEAD is how git knows what branch you are currently on and who the next parent will be
- It is a pointer to the name of the current branch
- But it could also point to a commit


#### Fixing Mistakes
- Git checkout
- Git reset
- Git revert
  - For shared repositories
- Git clean
- Git reset — hard HEAD


#### Amend a Commit
- Quick and easy shortcut that lets you make changes to the previous commit
- ex. If I forget to add a file or said something wrong in the commit message, I can do git commit — amend


#### Rebasing
- Give the commit a new parent
- Be on my own branch other than master
  - Git rebase master
  - This will change the HEAD to point to the master’s commit therefore sharing the same parent from master
