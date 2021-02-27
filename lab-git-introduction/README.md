# Introduction to git
Here the level of git  
![git_level](../screenshot/git-level.png)  
A ```working directory``` can have any number of subdirectories that form an overall workspace. (You might
also hear this referred to by similar names such as “working tree” or  “worktree.”)  
The ```staging area``` is one of the concepts in Git that many new users
have difficulty understanding and appreciating. At first glance, it may
seem like an unnecessary intermediate level that gets in the way of
trying to promote content from the working directory to the local
repository. In fact, it plays a significant role in several parts of Git's
functionality.  
There are 2 scenarios that originate with the user moving files into the stating area.  
The first is ```Prepare scenario```, suppose you have a large checklist of files to modify in order 
to create a feature or fix a bug. As pieces of the larger change are done, you move those pieces to the
staging area and check them off your list.
The second use case is the ```Repair scenario```. One of the interesting things that
Git allows users to do is to rewrite history.Effectively, it provides a do-over, or an opportunity to repair the
last commit.  
The workflow is essentially as follows:
* Make any updates in the working directory.
* Put the updates into the staging area.
* Run the commit with the option to amend.  

The ```local repository``` is the final piece of the set of Git levels that exist
on a user's local machine (the local environment). Once content has
been created or updated and then staged, it is ready to be committed
into the local repository.  
The ```remote repository``` is the level of Git that hosts and serves up
content for wider consumption. It's the place where multiple Git users
sync up the changes from their respective local repositories. It
corresponds to what you would traditionally think of as the server in
other source management systems.
![git_one_picture](../screenshot/git_one_picture.png)  
