# LAB 11
Working with Subtree
You’re going to add another repository as a subtree to super_calc.
```shell
git subtree add -P sub_docs --squash https://github.com/<your github repo>/sub_docs.git master 
```
Even though you don’t have much history in this repository, you
used the --squash command to compress it. Note that the -P
stands for prefix, which is the name your subdirectory gets.  

Check 
```shell
ls sub_docs
git log --oneline
```
Note that there is only one set of history here because there is only
one project effectively—even though we have added a repository as
a subproject.  

Now, you will see how to update a subproject that is included as a
subtree when the remote repository is updated. First, clone the
sub_docs project down into a different area.

```shell
cd .. 
git clone https://github.com/<your github user id>/sub_docs sub_docs_temp
cd sub_docs_temp
echo "readme content" > readme.txt
git add .
git commit -m "Adding readme file"
git push
```
Go back to the super_calc project 

```cd ../super_calc```  

To simplify future updating of your subproject, add a remote
reference for the subtree’s remote repository.  

```git remote add sub_docs_remote https://github.com/<your_github user id>/sub_docs```

You want to update your subtree project from the remote. To do
this, you can use the following subtree pull command.  

```shell
git subtree pull --prefix sub_docs sub_docs_remote master --squash
```
Because this creates a merge commit you will open an editor to enter 
a text comment. 

```shell
ls sub_docs
git log --oneline
```
Change the readme.txt file

```shell
cd sub_docs
echo "update" >> readme.txt
git commit -am "update readme"
```

Go back to super_project directory
```shell
cd ..
git subtree push --prefix sub_docs sub_docs_remote master
```
The next few steps show you how to take a subproject, put it onto a
different branch, and then bring that content into a separate
repository. First, use the subtree split command to take the content
from the sub_docs subproject and put it into a branch named
docs_branch in the super_calc area.

```git subtree split --prefix=sub_docs --branch=docs_branch```
```shell
git log --oneline docs_branch
cd ..
mkdir docs_proj
cd docs_proj
git init
```
Finally, use the git pull command in a slightly different context to
pull over that content into the master branch of your new project.

```shell
git pull ../super_calc docs_branch:master
gt log --oneline master
```















