# Compile and install git on centos 7
```shell
cd
git clone https://github.com/git/git.git  # download version of git 
git --version  # get the current version installed in the system
cd git  # change directory to the repo git
git log --tags --simplify-by-decoration --pretty="format:%ci %d" | grep 1.8.3.1 # check the version and date 
# pick up the latest version,  not a release candidate 
# it might find the version 2.30.1 
git checkout tags/v2.30.1 # get the version 
git branch  # check 

sudo yum -y install "@Development tools"  # install c compiler and tools
sudo yum -y install gettext-devel curl-devel perl-CPAN perl-devel openssl-devel zlib-devel # install packages
git  --version # get the version 
make configure # create the compile file
./configure --prefix=/usr/local # Generate the Makefile
nproc    # display the number of core  
make -j<value of nproc> #  make -j`nproc`  compile with the number of cores
make -j<value of nproc> test  # execute all tests
git --version  # get the version
sudo yum -y remove git  # removed the old version of git 
git --version  # get the version
sudo make install  # install the new version 
git --version  # Check 
# edit your file .bash_profile
use vi ou nano
# add the path to /usr/local/bin as below
PATH=$PATH:/usr/local/bin:$HOME/.local/bin:$HOME/bin

source ~/.bash_profile  # apply all changes defined in your .bashrc 
git --version # Check 
```