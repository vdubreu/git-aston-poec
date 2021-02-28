# Install a git project  SERVER and CLIENT

## Set up a git server on a remote machine
```shell
cd 
mkdir -p /home/centos/git-repo/project-1.git # create the project directory 
cd git-repo  # change directory
cd project-1.git  # change directory
git init --bare # init a git bare repository
# A bare Git repository is a repository that is created without a Working Tree
# it's a convention all repo created with bare terminated by .git
ls -alrt # check
```
## Set up the git client project on your local host in a directory not 
in your current pycharm project. 
```shell
cd ..  # move up 
mkdir project-1  # create the project directory
git init   # create the git environment
# non-bare repo has a .git folder
ls -alrt  #  check 
cd .git   # change directory
# compare with the remote directory 
ls -alrt # check
cd ..  
echo "# Project-1" > README.md # First file
git config --global user.name "First-name Last-name" # register name
git config --global user.email emailAddress@provider #  register email
git config --global core.autocrlf input # for Linux user
git status # check file is in working directory untracked
git add .  # the file is set in the staging area
git status # check file is now tracked, waiting for being committed
git commit  -m "First init" # the file is set in the local area
git status # check 
git remote add origin ssh://centos@<your_vm_ip_address>/home/centos/git-repo/project-1.git # change the url for git
git push -u origin master  # the file is sent to the remote git server
git status # check
```