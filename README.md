# Git-Version-Control

## Definitions
* Working copy - local copy where work
* Trunk/Main/Master - contains the main development branch
* Branch - line of development independent of another with a common history
* Head - get the latest version of the repository

  ## Configuration
  * config user name
    > git config --global user.name "BrandConstantin"
  * config email
    > git config --global user.email "b.c@gmail.com"

## Elementary commands for
* Clone repository 
  > git clone https://github.com/udacity/course-git-blog-project.git
* Init a project
  > git init
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
  
## Merge branches
* Chenge to main repository
  > git chckout main
* Merge the branches
  > git merge future-branch
* Send to the remote repository all the changes
  > git push origin main

## Create repository into remote and save to local
> git fetch && git checkout my-updates
* Change some file and apply changes: add, commit and push
> git push origin my-updates

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
* Create branch from other, in this case from master
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
    
## Log
* Show all commits
    > git log (use q to quit)
    > git log --stat
    > git log --online
    > git log --p
* Show 2 changes back 
    > git log --p -n 2
    > git log --since="2 weeks ago" --until="2 days ago"
    > git log --pretty=format:"%h - %an, %ar : %s"
    > git log -p fdf5393

## Show
* Show only one commit 
    > git show fdf5493 (use SHA, -p, -w, --patch, --state)

## Difference
* Show difference 
    > git diff
    > git difftool
* Show the changes in staging area, not in commit area
    > git diff --cached

## Tags
* Add tag to project 
    > git tag -a v1.0
    > git tag -a v1.5 -m "This is version1.5"
* Show all tag 
    > git tag
    > git show v1.5
* Delete tag 
    > git tag -d v1.0
* Add tag to a past commit 
    > git tag -a v1.0 a87894

## Revert/Alter/Erase
* Reverting commit 
    > git revert <sha-of-commit>
* Alter commit 
    > git commit --amend
* Erase previous commit 
    > git reset --hard HEAD~1

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

## Blame
* Who made the changes? 
    > git blame file1
* Who made the changes between line 6 and 8
    > git blame -L 6.8 index.html
* Show the email who made the changes
    > git blame --show-email file1

## Picking (very dangerous command)
* Reverse what we have launched 
    > git cherry-pick --abort
    > git cherry-pick --continue

## Rebase
* Condense all the changes of a project
    > git rebase --interactive --root

## Amend (you have to do git add again and then git commit again)
* If you commit but forget something 
    > git commit --amend

## Stash (to store in a temporary place what we have staging)
* Store “in a photo” what staging with git add
    > git stash
* To bring from staging area into local
    > git stash apply
