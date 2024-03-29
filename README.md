# Git-Version-Control
* Elementary commands for
* Clone repository 
    > git clone https://github.com/udacity/course-git-blog-project.git
* Get status
    > git status

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
* 3 steps to upload our changes
    * Add to staging area 
        > git add --all
        > git add .
    * Add to local repository 
        > git commit -m “initial commit”
    * Add to remote repository 
        > git push

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

## Branches
* Show all branches 
    > git branch
* Show all branches inclusive remote 
    > git branch -a
* Show all branches inclusive flags 
    > git branch -a -v
* Create branch 
    > git branch newbranch
* Create branch from other 
    > git branch newbranch master
    > git checkout -b otherbranch (create and switch to it all)
* Switch between branches 
    > git checkout otherbranch
* Delete branch 
    > git branch -d newbranch
* Force delete branch 
    > git branch -D newbranch

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

## Merge
* Join two branches 
    > git merge newbranch otherbranch
    > git merge newbranch master
* Share your code with others 
    > git push origin master

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

## Push
* Add to remote repository 
    > git push
* Add from local repository to remote repository
    > git push origin master
