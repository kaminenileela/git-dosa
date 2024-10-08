
* echo "Hello world" | git hash-object --stdin --> prints sha code on the screen 
* git cat-file <commit-id> -p --> print the info about sha code
* git checkout -b <branch-name> --> create new branch and change the workspace into new branch
* git log --oneline
* git checkout main ---> to move from another branch to main
* git rebase main --> when conflict araises pull main branch and do rebase to see what are the changes conflicting
* git rebase --continue ---> to see next changes. do necessary changes and commit.
* git status --> shows us status
* git diff <file name> ---> shows difference 
* git remote set-url origin <git repo url> ---> to change and set new remote url

Merging
--------
1. create another branch
2. do the changes in that branch
3. raise PR (pull request)
4. get the approval
5. then merge it 

Merge gives us a new merge commit which has 2 parents, we can clearly see the history.

![alt text](Merging.JPG)

Rebase
-----------
rebase --> change the base
no extra commit
commit id are changed
no history is preserved, it is rewritten as if it is done in main branch
looks clean, linear history

single branch --> multiple persons are working --> prefer merge
if you want to keep the history --> prefer merge
blindly go for merge, if you are not sure

single branch --> single person --> prefer rebase
if you dont want history --> prefer rebase
if you want clean structure --> prefer rebase

conflicts
----------------
if git findsout 2 different content in the same line, it cant take decission. people who wrote the code should sit together and resolve conflict

if main branch is moved forward
another branch is trying to merge the changes, then conflict will come


![alt text](rebase.JPG)

Before you raise PR, check main branch moved forward or not?
git checkout main 
git pull origin main

* pull before push.

git reset vs git revert
------------------------
Reset undo the changes, it is destructive operation. it will change the history and commit id. it has 3 types

1.soft
2.mixed
3.hard

index/staging/temp area --> git add

Lets suppose we did ---> git add . ; git commit -m ""

git reset --soft HEAD~1 --> soft will reset the commits, but keep the changes in staging area

git reset HEAD~1 --> mixed will reset the commit as well as remove changes from staging area but we can see changes in workspace.

git reset --hard HEAD~2---> resets the commit. changes commit, staging area and workspace.

revert
------
changes are pushed to remote, others pulled your changes already.
reset is not recommended if changes are already pushed to remote.
revert is safe if changes are pushed to remote already.revert will not change the history.
revert should not be done directly. it should be one by one and them commit after all are removed.



:%d
i-->to insert
esc :wq!