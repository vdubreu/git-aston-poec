# Lab 2

## Tracking content through the File Status Life Cycle
In this lab, you’ll work through some simple examples of updating files
in a local environment and viewing the files’ status and differences
between the various levels along the way.

```shell
# cd to your project-1
git status
git status -s
echo content > file3.c
git status
git status -s 
git add .
git status
echo change > file3.c
git status
git diff
git commit -m "comment"
git status
git add . 
git status 
echo "change 2" > file3.c 
git status
git diff
git diff --staged
git diff HEAD
git commit -am "committing another change"
git status
```