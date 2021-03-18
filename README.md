# Git Learning

![task_completed](/images/completed.jpg)
## commit 

`git commit`

## branch
`git branch newImage`  `git commit` :  * (head) will be on new commit

`git branch newImage`  `git check out newImage` `git commit` : main stays on previous commit & new branch move out with *


`git checkout -b [yourbranchname]`
 shortcut: if you want to create a new branch AND check it out at the same time
## merge
`git merge`
If you want to merge bugFix branch to main: on main, `git merge bugFix`

`git checkout bugFix` `git merge main`

#rebase
rebase: the advantage of rebasing is that it can be used to make a nice linear sequence of commits.

`git rebase main` make copy of bugFix branch's commit and join above main

checked out on the main branch (main*) (bugFix)
`git rebase bugFix`: main* join bugFix

## head
"Head" is the most recent commit
`checkout` to move "HEAD" around
Normally HEAD points to a branch name (like bugFix). When you commit, the status of bugFix is altered and this change is visible through HEAD.

HEAD -> main -> C1 `git checkout C1` HEAD -> C1

## relative ref ^ ~
`git log` to see hashes

Moving upwards one commit at a time with ^

ex) `main^` `main^^` 

Moving upwards a number of times with ~<num>
  
  `git branch -f main HEAD~3` move branches around (by directly reassigning a branch to commit with `-f` move by (force) )
  
## undo
`git reset` rewrites history (works for local branch)

ex) `git reset HEAD~1`

`git revert` (works for remote branch)
In order to reverse changes and share those reversed changes with others

## I want to work here and there
### cherry-pick
`git cherry-pick <commit1> <commit2> <...>`  to copy a series of commits below your current location (HEAD)
### you don't know what commits you wnat?
`rebase` `-i`
`git rebase -i HEAD~4`: on current HEAD, want to add commits to HEAD~4 

## juggling
reorder: `git rebase -i`
modify: `git commit --amend`
re-order the commits back: `git rebase -i`

## tag
`git tag v1 C1`

## describe
Git describe can help you get your bearings after you've moved many commits backwards or forwards in history; this can happen after you've completed a git bisect (a debugging search) or when sitting down at a coworkers computer who just got back from vacation

`git describe <ref>` (if ref not specfified, git uses HEAD)
output: <tag>_<numCommits>_g<hash>
 
 
 <tag> closest anchor tag in history
 
 <numCommits> how many commits away that tag is
 
 <hash> has of the commit being described
 
 ## rebasing multiple branches
 
## multiple bases
`git checkout main^2`


`git checkout` `HEAD` + `HEAD^2` + `HEAD~2` can be written
`git checkout HEAD~^2~2`

# Remote

## git clone

