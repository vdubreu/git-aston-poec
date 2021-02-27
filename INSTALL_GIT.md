# Compile and install git on centos 7
```shell
cd
git --version  # get the version 
sudo yum -y update # update all packages
sudo yum -y install wget  # install wget tool
wget  https://github.com/git/git/archive/v2.30.1.tar.gz # get the git repo
tar -zxvf v2.30.1.tar.gz  # untargzipped the repo
cd git-2.30.1 # change directory
sudo yum -y install "@Development tools"  # install c compiler and tools
sudo yum -y install gettext-devel curl-devel perl-CPAN perl-devel openssl-devel zlib-devel # install packages
git  --version # get the version 
make configure # create the compile file
./configure --prefix=/usr/local # Generate the Makefile
nproc    # display the number of core  
make -j<value of nproc> # compile on multi-core
make -j<value of nproc> test  # compile all tests
git --version  # get the version
sudo yum -y remove git  # removed all version
git --version  # get the version
sudo make install  # install the new version 
git --version  # Check 
source ~/.bash_profile  # change your .bashrc 
git --version # Check 
```