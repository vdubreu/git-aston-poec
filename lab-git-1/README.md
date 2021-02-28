# LAB 1
In this lab, you’ll use Git repository previously created on your local disk, and
stage and commit content into it. You’ll also explore the repository on
disk to see how content is mapped logically into the physical locations.

NOTE: If you are on Windows, you may have to enable showing hidden
files, files extension, and directories.

Got to your project-1 previously created

Create 2 files - their contents and names don't matter
```shell
echo content > file1.c
echo content > file2.c
# Stage the files with add comments
git add . 
# commit the file
git commit -m "My first file"
echo more >> file1.c
git commit -am "comment string"
# usage of plumbing command
git cat-file -t  <SHA1>
# print the content of that object
git cat-file -p <SHA1>
# take a note of tree line
# and go down to the tree line
```
The text mentions that Git sometimes
further compresses files to be more efficient. If you want to see this
in practice, run the following Git garbage collection command

```git gc```
