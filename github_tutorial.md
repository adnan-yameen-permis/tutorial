**Complete Merge + Rebase Process + Delete process**

1- Checkout to master branch

2- git merge branch name i,e git merge COL196

3- git branch -D COL196   // Remove the branch name from local

4- git push origin master // Push the changes to master

5- git push origin :COL196 // Delete branch from github

6- git checkout Existing Branch i,e git rebase master

7- git stash

8- git stash apply

**Remove a git commit which has not been pushed**
```
git reset HEAD~1
```
**See specific commit and revert it**
```
git checkout master
git log
# It will show a list of all commits
git show 1fb6b315a741520cdb1cb986ad25d2d8954481ef
git revert 1fb6b315a741520cdb1cb986ad25d2d8954481ef
```
**Get list of all modified files after specific date**
```
git log --since="2021-10-21" --name-only --pretty=format: | sort > changed-files.txt
```