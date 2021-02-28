# LAB 4
## Working with branches
In this lab, you'll start working with branches by creating a new branch
and making changes on it.

```shell
git branch  # check where you are 
echo "master version" >> file1.c 
echo "master version" >> file2.c
echo "master version" >> file3.c
git commit -am "master version"
# go to pycharm and check 
# go back to your project-1
git branch feature # create a branch but doesn't switch to it
git checkout feature
git branch    # check 
echo "new file ">  file4.c
echo "feature version" >> file1.c
echo "feature version" >> file2.c
echo "feature version" >> file3.c
git add . 
git commit -m "feature version "
git checkout master


```