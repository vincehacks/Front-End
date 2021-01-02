# GIT

Created by Vince Chang </br>

Here is where I post useful information on how to use GIT

GIT:
[GIT REPO w/ Notes](https://github.com/nnja/advanced-git)

#### NOTES

- Set up a text editor to open if you don’t pass -m in commit

```bash
git.io/config-editor
git config --global core.editor atom —wait
git config --global core.editor sublime -n -w
```

#### 3 AREAS OF WHERE CODE LIVES

1. Working Area
   - The files that are also not in your staging area, not handled by git
   - Also called “un-tracked files”
2. Staging Area
   - Aka the index or cache
   - This is how git knows what will change between the current commit and the
     next commit
3. Repository
   - All the files git knows about
   - Contains all the commits

#### MOVING FILES IN AND OUT OF THE STAGING AREA

```bash
git add <file> Adds a file
git rm <file> Removes a file
git mv <file> Renames a file
```

#### GIT STASH

- Save uncommitted work
- The stash is safe from destructive operations

```bash
git stash = stashes changes
git stash list = list changes
git stash show@{0} = show the contents
git stash apply = apply the last stash
git stash apply stash@{0} = apply a specific stash
git stash —include-untracked = keep untracked files
git stash —all = keep all files (even ignored ones)
git stash pop = remove the last stash and apply the changes
```

- Helpful to also name the stashes for easy reference

```bash
git stash save "WIP: This is a note / naming convention"
git stash branch <optional stash name>
git checkout <stash name> -- <filename> = grabs a single file from stash
```

- Cleaning the stash

```bash
git stash pop = remove the last stash and apply the changes, does not remove
with merge conflicts

git stash drop = remove the last stash
git stash drop stash@{n} = remove the nth stash
git stash clear = remove all stashes
```

- You can see the contents of a stash printed in the terminal with this command

```bash
git stash list // find which stash you would like to view, choose stash@{2}
git stash show stash@{2} // this prints the changes to the terminal
```

#### BRANCH

- Is a pointer to a particular commit
- The pointer of the current branch changes as new commits are made

#### HEAD

- `HEAD` is how git knows what branch you are currently on and who the next
  parent will be
- It is a pointer to the name of the current branch
- But it could also point to a commit

#### LOGS

- Use to find out your history

```bash
git log = full log history
git log --since="yesterday"
git log --since="2 weeks ago"
```

- Log files that have been moved or renamed

```bash
git log --name--status --follow -- <file>
```

- Use grep to help find messages embedded into a commit

```bash
git log --grep=mail --author=vincehacks --since=2.weeks

OR

git log --diff-filter=R --stat
R = Rename
M = Modified
D = Deleted
A = Added
```

- Referencing Commits

```bash
^ = first parent commit
^n = the nth commit

If there are multiple parents, then you can follow just the 1st parent:
~ = first commit back following 1st parent
~n = number of commits back, following only 1st parent
```

#### GIT SHOW

- Use these commands to see what you have worked on, can just use the UI on
  GitHub to do this instead of doing this on the command line, but this is how:

```bash
git show <commit> = shows commits and contents
git show <commit> -- stat = shows files changed in commit
git show <commit>:<file> = look at a file from another commit
```

#### GIT DIFF

- Shows you the changes:
  - Between commits
  - Between the staging area and the repository
  - What's in the working area

```bash
git diff = unstaged changes, what will not be in the next commit
git diff --staged = staged changes, what will be in the next commit

Show everything that is on branch B that is not on branch A:
git diff A B
OR
git diff A..B
```

- Check which branches have or have not been merged with master

```bash
git branch --merged master
git branch --no-merge master
```

#### FIXING MISTAKES

```bash
git checkout -- <file> =
  - Updates the staging area to match the commit and
  - Updates the working area to match the staging area
git checkout <commit> -- <file_path>
  - Copies both to working and staging area
git reset
git revert
  - For shared repositories
  - Creates a new commit that introduces the opposite changes from the specified
  commit
  - The original commit stays in the repository
  - Use revert if you are undoing a commit that has already been shared
  - Revert does not change history
git clean
  - Clear your working area by deleting untracked files
  - git clean --dry-run = tells you what will be deleted
  - git clean -d -f = deletes the file and directory
git reset — hard HEAD
  - Can run with or without a path
  - -mixed is the default
  - git reset ORIG_HEAD = undo a git reset
```

#### AMEND A COMMIT

- Quick and easy shortcut that lets you make changes to the previous commit
- Ex. If I forget to add a file or said something wrong in the commit message,

```bash
git commit — amend
```

#### REBASING

- Pull in all the latest changes from master, and apply our commits on top of
  them by changing the parent commit of our commits
- Rebase = Give the commit a new parent

```bash
git rebase master = will rewind to master, and apply your changes on top of it
```

- Works best for resolving merge conflicts
- Can use rebase to split commits that are too big using the rebase interactive

#### ABORT

- At any time before rebase is done, if things are going wrong:

```bash
git rebase --abort
```

#### REMOTES

- A remote is a git repository stored elsewhere - on the web, in Github, etc
- **Origin** is the default name git gives to the server you cloned from
- Cloning a remote repository from a URL will fetch the whole repository, and
  make a local copy in your `.git` folder

```bash
git remove -v = List out all the remotes
```

#### FORK

- Fork is a copy of a repository that's stored in your GitHub account
- You can clone or fork to your local computer
- If you want your cloned or fork repository to stay up-to-date on your local,
  you need to create something called an **upstream**

#### UPSTREAM

- The upstream repository is the base repository you created a fork from
- This isn't set up by default, you need to set it up manually
- By adding an upstream remote, you can pull down changes that have been added
  to the original repository after you forked/cloned it

#### FETCH

- Important for keeping your local repository up-to-date with a remote
- It pulls down all the changes that happened on the server
- But it does not change your local repository

#### PULL

- Does a fetch and a merge
- Pulling will pull down the changes from the remote repository to your local
  repository, and merging them with a local branch

```bash
git pull --rebase = Will fetch, update your local branch to copy the upstream
branch and then replay any commits you made via rebase
```

#### PUSH

- Pushing sends your changes to the remote repository
- Git only allows you to push if your changes won't cause a conflict

#### GIT FLOW

1. Fetch & Merge changes from the remote
2. Create a Branch to work on a feature
3. Develop Feature & Commit work
4. Fetch & Merge from the remote
5. Push Branch to Remote for review

#### USEFUL GIT COMMANDS

| Command                              | Purpose                                                              |
| ------------------------------------ | -------------------------------------------------------------------- |
| `git log`                            | Shows history                                                        |
| `git checkout HEAD filename`         | Discards changes in working directory                                |
| `git reset HEAD filename`            | Un-stages file changes in the staging area                           |
| `git reset commit-SHA`               | Resets to previous commit of your choice with SHA # found in git log |
| `git commit --amend -- reset-author` | Fixes Identity for email                                             |
