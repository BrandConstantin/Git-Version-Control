# Git-Version-Control

Version control system / source code manager abbreviated as VCS is a tool that manages different versions of source code.

## Advantages:
* They are scalable for complex development projects
* They allow for the creation and management of backups
* They make it easier for developers to synchronize with the latest version
* They allow for code audits, isolated testing, and version history maintenance

## Terminology
* Working copy - local copy where work
* Trunk/Main/Master - contains the main development branch
* Branch - line of development independent of another with a common history
* Head - get the latest version of the repository
* Repository - it is the place where all the information of a project is stored, usually in  the form of a tree. Is the directory which contains your project work
* Sha is an id number for each commit.
* Checkout is when content in the repository has been copied to the workig directory.
* Staging area / staging index / index a file in the git directory that stores information about what will go into your next commit.
* Commit -> save the state of your project in Git

## Steps to work
* Create a new branch from other 
  > git checkout -b myfeature master
* Switch to the new branch
  > git checkout myfeature
* Show the status
  > git status
* Add all
  > git add .
* Initial commit
  > git commit -m “initial commit”
* Join the remote branch with local
  > git merge --no-f myfeature
* Bring the changes made from others
  > git pull
* Push from local to remote to share with others (only the first time)
  > git push origin myfeature

## Git Configuration
### First time configuration
* Tags: --local, --global, --system
* config user name
  > git config --global user.name "BrandConstantin"
* config email
  > git config --global user.email "b.c@gmail.com"
* config password (the password save in text plain)
  > git config --global user.password "Hdfi43245#~2s"
* Edid the configuration
  > git config --global --edit
* Create keyboard shortcuts, in this example "ci" for commit
* Alias for: alias.co (checkout), alias.br (branch), alias.st (status), alias.ci
  > git config --global alias.ci commit
* Select text editor
  > git config --global core.editor vim
* Text editor like Sublime for Win 64 bits
  > git config --global core.editor "'c:/program files/sublime text 3/sublimetext.exe' -w"
* For merge tools
  > git config --global merge.tool kdiff3
* Show colored git (color.ui, color.diff, color.branch, color.grep, color.status, color.showBranch)
* Colors: black, red, green, yellow, blue, magenta, cyan, white
  > git config --global color.ui false
* Makes sure that Git output is colored
  > git config --global color.ui auto
* Displays the original state in a conflict
  >  git config --global merge.conflictstyle diff3
* Config list
  > git config -list

## Elementary commands for
* Clone repository 
  > git clone https://github.com/udacity/course-git-blog-project.git
* Init a project
  > git init
* To create a remote and central repository where the commit it is imposible to realize directly
  > git init --bare
* Get status of your local repository
  > git status
* Another form of graphical form to get the status of your local repository
  > git status -s
* Add the changes to staging area
  * One file 
  > git add localfile.txt
  * For all the changes
  > git add --all
  * Another way for all the changes
  > git add .
* Confirm the changes and prepare a history
  > git commit -m "initial commit"
* Send changes from local to remote (GitHub, GitLab or Bitbucket servers)
  > git push origin main
  * if isn't the first time pushing
  > git push
* Merge the file from your remote repository into your local repository
  > git pull --all
    
## New branch
* Create a new branch
  > git branch future-branch
* Use the new branch
  > git checkout future-branch

## Create repository into remote and save to local
> git fetch && git checkout my-updates
* Change some file and apply changes: add, commit and push
> git push origin my-updates
* Establish the remote repository
> git remote add origin <url repo GitHub>
* Show if the login with the github is ssh type or other
> git remote show origin

## Branches
* Create branch
  > git branch test1
* Show all branches 
  > git branch
* Show all branches inclusive remote 
  > git branch -a
* Show all branches inclusive flags 
  > git branch -a -v
* When push the first time
  > git push origin test1
* Create new branch from other branch, in this case from master
  > git branch newbranch master
* Create branch and switch to 
  > git checkout -b otherbranch
* Switch between branches 
  > git checkout otherbranch
* Delete branch 
  > git branch -d newbranch
* Force delete branch 
  > git branch -D newbranch

## Pull
* Get all changes remotely to local
  > git pull

## Merge
* Merge from master to other branch
  > git merge master newbranch
* Share your code with others, send from local to remote
  > git push origin master
The editor has the following merge conflict indicators:
```
<<<<<<< HEAD everything below this line (until the next indicator) shows you what's on the current 
branch
||||||| merged common ancestors everything below this line (until the next indicator) shows you what the
original lines were
======= is the end of the original lines, everything that follows (until the next indicator) is what's on the
branch that's being merged in
>>>>>>> heading-update is the ending indicator of what's on the branch that's being merged in (in this case, the heading-update branch)
```

## Reset (used to undo a commit or snapshot prepared with commit)
* Alter commit 
  > git commit --amend
* Erase previous commit (never used)
  > git reset --hard HEAD~1
* Reset all at the confirmation that need, erase the other one
  > git reset --soft 52f823c
* Reset multiple
  > git reset 1a6a403
* To show the reference records of the resets performed
  > git reflog
* To reset and restore from a Head point
  > git reset --hard HEAD@{3}

## Revert
* Reverting commit, revert changes made by a commit
  > git revert <hash>
  
## Log
* Show all commits (use q to quit), with his author, name of branches etc
  > git log
* Get his author, name of branches etc, and number of deleting and adding
  > git log --stat
* All the commits with name and hash only
  > git log --online
* to show some details that are hidden from the default view
  > git log --online --decorate
*   After a date
  > git log --after 2024-08-28
* Before a date
  > git log --before "yyyy-mm-dd"
* By number of confirmation, in this case the last 10 confirmations
  > git log -10
* By author
  > git log --author="Alana"
* By a string
  > git log --grep="ticket"
* Show the last 2 changes 
  > git log -n 2
* From and To
  > git log --since="2 weeks ago" --until="2 days ago"
* Pretty format
  > git log --pretty=format:"%h - %an, %ar : %s"
* Show a commit with his changes in pretty format
  > git log -p 1c3e78f6
* Show the changes, added and deleted
  > git log -p
  
## Show
* Show only one commit, with his chenges and all the information (use SHA, -p, -w, --patch, --state)
  > git show 1c3e78f6

## Difference
* Show difference 
  > git diff a/file.txt b/file.txt
* Highlight changes
  > gir diff --color-words
* All changed from the last confirmation
  > git diff
* campare between two confirmations (git log --pretty=oneline)
  > git diff 957fbc92b123030c389bf8b4b874522bdf2db72c ce489262a1ee34340440e55a0b99ea6918e19e7a
* Compare branches
  > git diff branch1...other-feature-branch
* Compare a file between two branches
  > git diff main new_branch ./diff_test.txt
  > git difftool
* Show the changes in staging area, not in commit area
  > git diff --cached ./path/to/file

## Stash (to store in a temporary place, in staging)
* Store “in a photo” what staging with git add
   > git stash
* Apply the changed from a stash
  > git stash pop
* Apply the changed from a stash
  > git stash pop stash@{2}
* To bring from staging area into local, and ready to commit 
   > git stash apply
* Add to stash untracked files
  > git stash -u (or --include-untracked)
* Add to stash ignored files
  > git stash -a
* List of stash
  > git stash list
* Save stash with a message
  > git stash save "add style to our site"
* Show difference between stash
  > git stash show
* Show difference between all stash
  > git stash show -p (or --patch)
* Create branch from a stash
  > git stash branch add-stylesheet stash@{1}
* Drop a stash
  > git stash drop stash@{1}
* Delete all the stash
  > git stash clear
  
## Gitignore patterns:
* Mark line as a comment with #
* A file that was previously commited
  > git rm --cached debug.log | git commit -m "start ignore this file"
* To force a ignored file
  > git add -f debug.log
* All directory with this name
  > **/logs
* All this files in a directory name logs
  > **/logs/debug.log
* All the files with this extension
  > .log
* With a match character (yes debug0.log and debug1.log but not debug10.log)
  > debug?.log
* Match with this coincidence
  > debug[0-9].log
* Not match with this coincidence (yes debug2.log but not debug0.log, debug1.log or debug01.log)
  > debug[!01].log
* Math with any file and directory with this name
  > logs
* Ignore all the directory with this name
  > logs/
* With the one or more directory (logs/debug.log, logs/monaday/pm/debug.log)
  > logs/**/debug.log
* Ignore directory with the name (yes logs/monday/debug.log but not logs/latest/debug.log)
  > logs/*day/debug.log
* For escape characters, in this case file foo[1].txt
  > foo\[1\].txt
    
## Tags (it's like a branch that never change, and used for publish a version)
* Add tag to project 
  > git tag -a v1.0
* Add a tag with a message
  > git tag -a v1.5 -m "This is version 1.5"
* Show all tag 
  > git tag
* Show a tag
  > git show v1.5
* Show tags that have a match
  > git show -l *-rc*
* Tag an old commit
  > git tag -a v1.2 ab45d0y
* Add to origin a tag
  > git push origin v1.4
* Checkout
  > git checkout v1.3
* Delete tag 
  > git tag -d v1.0

## Blame
* Who made the changes? 
  > git blame file1
* Who made the changes between line 6 and 8
  > git blame -L 6.8 index.html
* Show the email who made the changes
  > git blame --show-email file1
    
## Undo changes (only in commit area)
* Undo changes for a group of files 
  > git checkout -- .
* Undo changes for a file 
  > git checkout -- file1
  > git checkout HEAD -- .

## Undo changes (only in staging area)
* Undo a file 
  > git reset HEAD file1
* Delete all in staging and go to a previous status
  > git reset --hard HEAD~1
* Reverse SHA 
  > git revert 434bg1
* Reverse from a HEAD to another 
  > git revert HEAD...HEAD~2 --no-edit

## Picking (very dangerous command)
* Reverse what we have launched 
 > git cherry-pick --abort
* Continue to commit 
 > git cherry-pick --continue
* Combine with other commit
 > git cherry-pick 054af4g

## Rebase
* Condense all the changes of a project
 > git rebase --interactive --root

## Amend (you have to do git add again and then git commit again)
* If you commit but forget something 
 > git commit --amend
    
## Types creating the branch
Example: feat/actualizaciones/main/ticket-13654
* feat: a new feature
* fix: a bug fix
* docs: changes to documentation•style: formatting, missing semi colons, etc; no code change
* refactor: refactoring production code
* test: adding tests, refactoring test; no production code change
* chore: updating build tasks, package manager configs, etc; no production code change
