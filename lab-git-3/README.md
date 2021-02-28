# Lab 3
## Using Git history, Tags and Aliases
In this lab, you'll work through some simple examples of using the git
log command to see the flexibility it offers, and also create an alias to
help simplify using it. You'll also look at how to tag commits to have
another way to reference them.

```shell
echo new >> file1.c 
git commit -am "add a line"
git log 
git status -s 
git log --oneline
# Alias 
git log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
git lg
git lg file1.c
git diff <SHA1>..<SHA1>
git tag first <SHA1>
git tag last <SHA1>
git diff first..last
```