link: https://github.com/github/training-kit/blob/master/downloads/github-git-cheat-sheet.md

## Install Git
GitHub provides desktop clients that include a graphical user interface for the most common repository actions and an automatically updating command line edition of Git for advanced scenarios.

### GitHub Desktop
https://desktop.github.com/

Git distributions for Linux and POSIX systems are available on the official Git SCM website.

### Git for all platforms
http://git-scm.com

## Configure tooling
Configure user information for all local repositories

```$ git config --global user.name "[name]"```

Sets the name you want attached to your commit transactions


```$ git config --global user.email "[email address]"```

Sets the email you want attached to your commit transactions


## Create repositories
Start a new repository or obtain one from an existing URL


```$ git init [project-name]```

Creates a new local repository with the specified name


```$ git clone [url]```

Downloads a project and its entire version history


## Make changes
Review edits and craft a commit transaction


```$ git status```

Lists all new or modified files to be committed


```$ git diff```

Shows file differences not yet staged


```$ git add [file]```

Snapshots the file in preparation for versioning


```$ git diff --staged```

Shows file differences between staging and the last file version


```$ git reset [file]```

Unstages the file, but preserves its contents


```$ git commit -m"[descriptive message]"```

Records file snapshots permanently in version history

## Group changes
Name a series of commits and combine completed efforts


```$ git branch```

Lists all local branches in the current repository


```$ git branch [branch-name]```

Creates a new branch


```$ git checkout [branch-name]```

Switches to the specified branch and updates working directory


```$ git merge [branch-name]```

Combines the specified branch’s history into the current branch


```$ git branch -d [branch-name]```

Deletes the specified branch

## Refactor file names
Relocate and remove versioned files


```$ git rm [file]```

Deletes the file from the working directory and stages the deletion


```$ git rm --cached [file]```

Removes the file from version control but preserves the file locally


```$ git mv [file-original] [file-renamed]```

Changes the file name and prepare it for commit

## Suppress tracking
Exclude temporary files and paths

```
*.log
build/
temp-*
```

A text file named `.gitignore` suppresses accidental versioning of files and paths matching the specified patterns


```$ git ls-files --others --ignored --exclude-standard```

Lists all ignored files in this project

## Save fragments
Shelve and restore incomplete changes


```$ git stash```

Temporarily stores all modified tracked files


```$ git stash pop```

Restores the most recently stashed files


```$ git stash list```

Lists all stashed changesets


```$ git stash drop```

Discards the most recently stashed changeset

## Review history
Browse and inspect the evolution of project files


```$ git log```

Lists version history for the current branch


```$ git log --follow [file]```

Lists version history for the file, including renames


```$ git diff [first-branch]...[second-branch]```

Shows content differences between two branches


```$ git show [commit]```

Outputs metadata and content changes of the specified commit

## Redo commits
Erase mistakes and craft replacement history


```$ git reset [commit]```

Undoes all commits after `[commit]`, preserving changes locally


```$ git reset --hard [commit]```

Discards all history and changes back to the specified commit

## Synchronize changes
Register a remote (URL) and exchange repository history


```$ git fetch [remote]```

Downloads all history from the remote repository


```$ git merge [remote]/[branch]```

Combines the remote branch into the current local branch


```$ git push [remote] [branch]```

Uploads all local branch commits to GitHub


```$ git pull```

Downloads bookmark history and incorporates changes


---
___

link: https://raw.githubusercontent.com/jakubpawlowicz/git-cheat-sheet/master/README.md

#### Go one step back in history
```shell
git checkout @~1
```

#### Show commit changes
```shell
git show <commit-sha>
```

#### Push master branch to origin
```shell
git push origin master
```

#### List all branches
```shell
git branch -a
```

#### List remote branches
```shell
git branch -r
```

#### Sync list of remote branches
```shell
git remote update
```

#### Checkout remote branch into local repository
```shell
git checkout -t -b <local-name> <remote-name>
```

#### Create a branch
```shell
git checkout -b <name>
```

#### Push local branch to remote
```shell
git push origin <remote-name>
```

#### Merge two branches
```shell
git checkout <target>
git merge <source>
```

#### Merge two branches with squash
```shell
git checkout <target>
git merge --squash <source>
```

#### See what branches are merged into master
```shell
git branch -r --merged master
```

#### Ignore files globally
https://help.github.com/articles/ignoring-files

#### pull changes from the server + rebase (equivalent of git stash save && git pull && git stash pop && git push) + push
```shell
git pull --rebase && git push
```

#### Set up git inet server
```shell
git daemon --base-path /home/git --verbose
```

#### Add remote origin
```shell
git remote add origin <url>
```

#### Fix 'branch not tracking anything'
```shell
git config --add branch.master.remote origin
git config --add branch.master.merge refs/heads/master
```

#### Extract patch from a given file
```shell
git diff --patch-with-raw rev1 rev2 patched_file > diff_file
```

#### Diff with paging
```shell
GIT_PAGER='less -r' git dc
```

#### Apply a patch
```shell
git apply diff_file
```

#### Publish branch
```shell
git push origin <name>
```

#### Delete remote branch
```shell
git push origin :<name>
```

#### Cherry-pick a commit
```shell
git cherry-pick -n <sha>
```

#### Revert commit
```shell
git revert -n <sha>
```

#### Reset HEAD to n commits back
```shell
git reset --hard HEAD~<n>
```

#### Squash N last commits
```shell
git rebase --interactive --autosquash HEAD~N
```

#### search git log commits
```shell
git log -S “free text”
```

#### remove file from history (can use 'git rm -rf…' to remove files recursively)
```shell
git filter-branch --index-filter 'git rm --cached --ignore-unmatch <path to file>' --prune-empty --tag-name-filter cat -- --all
git push origin master --force
rm -rf .git/refs/original/
git reflog expire --expire=now --all
git gc --prune=now
git gc --aggressive --prune=now
```

#### Prune history
```
git gc
git gc --aggressive
git prune
```

#### Checkout GitHub PR
```shell
git fetch origin pull/1234/head:local-branch-name
```

#### Convert long sha to short one
```shell
git rev-parse --short <sha>
```

#### My aliases
```shell
git config --global alias.aa "add --all"
git config --global alias.ai "add --interactive"
git config --global alias.b "branch"
git config --global alias.ba "branch -a"
git config --global alias.c "commit"
git config --global alias.ca "commit --amend"
git config --global alias.cf '!sh -c "git commit --fixup $@"'
git config --global alias.co "checkout"
git config --global alias.col '!sh -c "git checkout -b $@"'
git config --global alias.cor '!sh -c "git checkout --track -b $@ origin/$@"'
git config --global alias.cp "cherry-pick"
git config --global alias.cpa "cherry-pick --abort"
git config --global alias.cpc "cherry-pick --continue"
git config --global alias.cs '!sh -c "git commit --squash $@"'
git config --global alias.d "diff"
git config --global alias.dc "diff --cached"
git config --global alias.ds "diff --stat"
git config --global alias.dsc "diff --stat --cached"
git config --global alias.fpr '!sh -c "git fetch origin pull/$@/head:$@-pr"'
git config --global alias.l "log"
git config --global alias.lf "log --follow"
git config --global alias.lg "log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %Cblue<%an>%Creset' --abbrev-commit --date=relative --all"
git config --global alias.m "merge"
git config --global alias.mb "merge-base master HEAD"
git config --global alias.ms "merge --squash"
git config --global alias.pl "pull"
git config --global alias.ps "push"
git config --global alias.psc '!sh -c "git push --set-upstream origin \$(git rev-parse --abbrev-ref HEAD)"'
git config --global alias.psd '!sh -c "git push origin :\$(git rev-parse --abbrev-ref HEAD)"'
git config --global alias.psf "push --force-with-lease"
git config --global alias.r "reset HEAD"
git config --global alias.rb "rebase"
git config --global alias.rba "rebase --abort"
git config --global alias.rbc "rebase --continue"
git config --global alias.rbi "rebase --interactive --autosquash"
git config --global alias.rbm "rebase --interactive --autosquash origin/master"
git config --global alias.rh "reset --hard"
git config --global alias.rs "reset --soft"
git config --global alias.s "status"
git config --global alias.sh "show"
git config --global alias.shs "show --stat"
git config --global alias.st "stash"
```

#### Global git ignore
```shell
git config --global core.excludesfile ~/.gitignore
```

#### Global username & email
```shell
git config --global user.name "Jakub Pawlowicz"
git config --global user.email '<email>'
```

#### Local username & email
```shell
git config user.name "Jakub Pawlowicz"
git config user.email '<email>'
```

####
```shell
git config --global color.diff auto
git config --global color.status auto
git config --global color.branch auto
```

#### Branch name and merge status in bash prompt (should go to local or global bash profile)
```shell
function parse_git_dirty {
  [[ $(git status 2> /dev/null | tail -n1) != "nothing to commit, working directory clean" ]] && echo "*"
}
function parse_git_branch {
  git branch --no-color 2> /dev/null | sed -e '/^[^*]/d' -e "s/* \(.*\)/[\1$(parse_git_dirty)]/"
}
export PS1='\u@\h \[\033[0;36m\]\w \[\033[0;32m\]$(parse_git_branch)\[\033[0m\]$ '
```