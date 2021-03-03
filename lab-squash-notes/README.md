# LAB Squash and Notes

##Squashing your commits

Go to your project   
Checkout a branch  
```git checkout -b squash-branch```
let's create 2 commits in the new branch , which we can squash together. 
```shell
echo "1" >> README.md
git add .
git commit -m "wip1"
echo "2" >> README.md
git add .
git commit -m "wip2"
# check 
git log --oneline
```
We want the wip1 and wip2 commits to be squashed into one commit with a nice
commit message. You can do this using the following command

```git rebase -i HEAD~2```

HEAD~2 means that we want to have the last two commits squashed. If you want to
have four commits squashed, the command will end in HEAD~4. Keep in mind that
at least two commits are required in order to perform a squash operation.

Your editor will get opened. You have to change the word ```pick``` to ```squash``` in the
second line. 

Now save the file, and close the editor
git will now open another editor window add a message
Save the file

```git push origin squash-branch```

## Notes

Fork and clone 
git clone https://git.eclipse.org/r/jgit/jgit
Checkout a branch  

```git checkout -b notesMessage --track origin/stable-3.2```
List the commit hash    

```git log -1```

Change the commit message by amending the commit using  

``` git commit --amend```

So, the commit hash will change  when updating the commit message.

As you can see from the output of Pycharm, our branch has diverged from
origin/stable-3.2  
To prevent this result we can add a note to the commit message 
First we are going to reset the branch and add a note to the commit 
```shell
git reset --hard origin/stable-3.2
git notes add -m "update manisfest files"
# check 
git log -1
```
### How to manage notes
```shell
git notes add -m "Update MANIFESTS files for next version"
# add note to an existing one
git notes add -f -m "Update MANIFESTS files for next version"
# append 
git notes append -m "Verified by hme"
# check 
git log -1 --notes --oneline


```
### Separating notes by category
```shell
git checkout -b notesReferences --track origin/stable-3.1
git log -10 --oneline
# add a note for 
git notes add -m "test note"
# add ref notes
git notes  --ref alsoCherryPick add -m "570bba5" b4f07df
git log -1 b4f07df357fccdff891df2a4fa5c5bd9e83b4a4a --notes=alsoCherryPick
```
As you see from the output, Git shows the alsoCherryPick notes. Git
defaults to adding notes to refs/notes/commits, but we have explicitly
specified to show alsoCherryPick. It would be nice if you could show the
alsoCherryPick notes' reference by default so you don't have to use --
notes=alsoCherryPick. This can be done by configuring Git as follows:  


```git config notes.displayRef "refs/notes/alsoCherryPick"```

:



