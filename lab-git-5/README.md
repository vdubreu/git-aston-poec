# LAB 5
## Practising with merging 
In this lab, you'll work through some simple branch merging.

```shell
git status  # working tree must be clean
# you should be in a master branch
echo "Initial content" > file5.c 
git add .
git commit -m "adding new file on master"
git branch newbranch
echo "update on master" > file5.c 
git add . 
git commit -m "update on master"
git checkout newbranch
echo "update on newbranch" > file5.c 
git commit -am "update on newbranch"
git checkout master
git merge newbranch
git status
cat file5.c
# resolve the conficts
echo "merged version" > file5.c
git add .
git commit -m "Fixed conflicts"
git status
# check pycharm project
git branch -d newbranch

```