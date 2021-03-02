# LAB 8
You cloned a repository from
GitHub into two different directories on your local system: calc2
and calc_other. You’ll use these two directories to simulate two
users working against the same remote repository. Change into the
calc_other directory.

```shell
cd calc_other
```
First, you need to set up a local
features branch, so create a local branch that tracks the remote
features branch.

```shell
git branch features origin/features
```
Look at what features are available for you to use 
```shell
 git log --oneline features
```

Now, let’s create a temporary branch to use as we work on
incorporating these features. Create a new branch cpick and switch
to it in one step using the shortcut. (cpick here represents “cherry
pick”)

```git checkout -b cpick```

Issue the command to cherry-pick that commit’s SHA1 value onto your current branch.
 
```git cherry-pick d003b91```

A message appears that the function is being added. Assuming
there are no errors, run a log of your current branch.

```git log cpick --oneline```

Open your browser and check if you have the max function

Now you can use ```rebase``` to incorporate the exp and min functions
Look at what features are available for you to use 
```shell
 git log --oneline features
```
Now we are going to use ```rebase```, in this way we will have the functionnality
incorporated as well as the history, find the SHA1 value for the min function. 

```shell
git rebase 3753e5a
git log --oneline
# Check your web browser
```
We are now ready to merge the branch back into the master branch
```shell
git chechkout master
git merge cpick 
```
once the merge is complete , push the changes out to the remote. 
```git push```

You are done simulating the activity of user one. Now, you can
move on to working as user two in the calc2 area. Change to the
calc2 subdirectory.

```cd ../calc2```

User 2 wants to merge the ui work from origin/ui into the master
branch to promote it. For convenience, you first need to create a
local ui branch from the remote branch.

```shell
git branch ui origin/ui
git branch   # you are in the master 
git merge ui
git push origin master # push the updates out to the remote 
```
your push is rejected 
You could do a force
push (with the -f option), but that is often dangerous  
Do a pull to see if it can merge cleanly.  
```git pull origin master```  
You have now a merge conflict  
```git merge --abort```  
Recall that the fetch command updates the remote
tracking branches but not the local branches. So, you execute a
fetch command.  
  ```git fetch``` 
You are now ready to try the rebase. If all goes well, this operation
will rebase locally off of the updated content from the master in the
remote tracking branches. Run the following command (making
sure you are in the master branch when you do so):

```shell
git rebase origin master
# you have some conflits 
# abort the rebase
git rebase --abort
```

Once again, conflicts arise. Because the changes are different,
between adding functionality and changing ui features, you can
make an educated guess that if you just keep the current changes
and apply the other changes on top of them, you won’t run into
critical conflicts. So, you can tell Git to keep your changes if there
are perceived conflicts. The easiest way to do that is to add the -
Xours option. Recall that this option passes the “keep ours if
there’s a conflict” option to the default recursive strategy. Abort the
current rebase operation, and run the command again with the
extra option.

```shell
git rebase -Xours origin master
git log --oneline
git push
```
















