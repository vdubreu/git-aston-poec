# LAB 10 
working with submodules
in a super_calc directory

```shell
git submodule add https://github.com/<your github_userid>/sub_ui.git sub_ui
ls 
git status
git show :.gitmodules
```
Now you need to commit and push the staged submodule mapping
and data to your local and remote repositories. Run the following
commands:

```shell
git commit -m "Add submodule sub_ui"
git push
```

Now you can clone a new copy of this project with the submodule.
Change to a higher-level directory and clone a copy of the project
down as super_calc2.

```shell
cd ..
git clone https://github.com/<your github_userid>/super_calc super_calc2
```
Change into the super_calc2 directory and look at what’s in the
sub_ui subdirectory. Run the submodule status command to see
what the status of the submodule is.

```shell
cd super_calc2
ls sub_ui
git submodule status
```
Notice the hyphen (-) in front of the SHA1 value. This indicates
that the submodule has not been initialized yet relative to the super
project. You could have done this at clone time using the --
recursive option. However, because you didn’t, you need to use the
update --init subcommand for the submodule operation, as
follows:

```
git submodule update --init
```
Git clones the sub_ui code into the submodule. Look at the sub_ui
subdirectory to see the contents, and then run the submodule
status command again.

```shell
ls sub_ui
git submodule status
```

This time, you see a space at the beginning (instead of the minus
sign) to indicate the submodule has been initialized
Now, you need to make a simple update to the code in the
submodule. Change into the sub_ui subdirectory (cd sub_ui) and
edit the calc.html file there as follows: change the line
<title>Advanced Calculator</title>
in the file to
<title> your_name_here Advanced Calculator</title>
substituting your actual name for “your_name_here”. Save your
changes.

```shell
git commit -am "Update title"
git log --oneline
cd ..
git submodule status

```

Note that the submodule SHA1 reference now points to your latest
commit in the submodule, but there is a plus sign (+) at the front of
the reference. This indicates that there are changes in the
submodule that have not yet been committed back into the super
project. Run a git status command to get another view of what’s
changed for the super project.

```git status``` 

The status command gives you much more information about
what’s changed. It tells you that the sub_ui module has been
changed and is not updated or staged for commit. To complete the
update, you need to stage and commit the sub_ui data. You can
then push it out to your GitHub remote repository. To complete the
process, execute the commands below.

```shell
git commit -am "Update for submodule sub_ui"
git push
```

Now that you’ve updated the submodule and the supermodule,
everything is in sync. Run a git status and a git submodule status
command to verify this.

```shell
git status
git submodule status
```
