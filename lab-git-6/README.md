# LAB 6
 Deleting, Renaming stashing

## Deleting
```shell
echo "another one" > file6.c
git add .
git commit -m "yet another lab file"
# you decide to remove the file
git rm file6.c 
git status
ls  # to find out whether the local file is still there. 
# you change yout mind. you want the file back 
git reset --hard HEAD
git status
git rm file6.c 
git commit -m"delete file"
git status
```

## Renaming
```shell
mkdir myfolder
git add .
git status 
# if a directory is empty, git does nothing
touch myfolder/test.c 
git add .
git status 
git mv myfolder mynewfolder
# if you want to overwrite an existing folder , add  -f in the previous command
git add -u mynewfolder # -u it's updated already tracked files
```

## Stashing
```shell
echo "one more" > file7.c
git add file7.c
git status
#you need to quit working with this file temporarily and fix other files
# save off the current state with the stash command.
git stash
git status
ls 
git stash list
# make a change 
echo update >> file5.c
git commit -am "update file"
# restore your previous state
git stash pop 
git status
ls
```



