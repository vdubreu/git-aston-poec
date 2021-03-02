# LAB 9 
Working with worktrees
Log in to your GitHub account and 
fork the three projects from the following listed locations.

https://github.com/master-afip/super_calc.git
https://github.com/master-afip/sub_ui.git
https://github.com/master-afip/sub_docs.git

in your project_aston directory clone the super_calc.git 
```cd super_calc```

In this case, you want to work on both the master branch and the
features branch at the same time. You can work on the master
branch in this directory, but you need to create a separate working
tree (worktree) for working on the features branch. You can do that
with the worktree add command, passing the -b to create a new
local branch off of the remote tracking branch.
```shell
git worktree add -b features ../super_calc_features origin/features
cd ../super_calc_features
# Edit the file calc.html
# 
<title>Calc</title>
to
<title> github_user_id's Calc</title>
#
git commit -am "Updating title"
cd ../super_calc
git branch 
git log --oneline features
git worktree list 
rm -Rf ../super_calc_features
git worktree prune
```

