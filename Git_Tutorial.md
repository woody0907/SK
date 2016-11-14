[TOC]
Git is a distributed revision controll and source code management system with an emphasis on speed. Git is a fredd sotfware distributed under the terms of GNU General Public License version 2.

This Tutorial will help beginners learn the basic functionality of Git version controll system. After completing this tutorial, you will find yourself at a moderate level of expertise in using Git from where you can take yourself to the next levels.

##Git - Basic Concepts
###Version Control System
VCS is a software that helps software developers to work together and maintain a complete history of their work.

Listed below are the functions of a VCS:

- Allows developers to work simultaneously
- Does not allow overwriting each other's changes.
- Maintains a history of every version

Following are the types of VCS:

- Centralized version control system(CVCS)
- Distributed/Decentralized version control system(DVCS)

###DVCS
VCSC uses a central server to store all files and enables team collaboration. But the major drawback of CVCS is its single point of failure, i.e., failure of central server. Unfortunately, if the central server goes down for an hour, then during that hour, no one can collaborate at all. And even in a worst case, if the disk of the central server gets corrupted and proper backup has not been taken, then you will lose the entire history of the project. Here, DVCS comes into picture.

DVCS client not only check out the latest snapshop of the directory but the also fully mirror the repository. If the server goes down, then the repository from any client can be copied back to the server to restore it. Every checkout is a full backup of the repository. Git does not rely on the central server and that is why you can perform many operations when you are offline. You can commit changes, create branches, view logs, and perform other operations when you are offline. You require network connection only to publish your changes and take the latest changes.

###Advantages of Git
####Free and open source
Git is released under GPL's open source license. It is available freely over the internet. You can use Git to manage property pojects without paying a single penny. 
####Fast and small
As most of the operations are performed locally, it give a huge benefit in terms of speed. There is no need to interact with the remote server for every operation.
The core part of Git is written in C, which avoid runtime overheads associated with other high level languages. Though Git mirros entire repository, the size of the data on the client side is small. This illustrates the effeciency of Git at compressing and storing data on the client side.
####Implicit backup
The changes of losing data are very rare when there are multiple copies of it. Data present on any client side mirrors the repository, hence it can be used in the event of a crash or disk corruption.
####Security
Git use a common cryptographic hash function called secure hash function (SHA1), to name and identify objects withing its database. Every file and commit is checksumed and retrieved by its checksum at the time of checkout. It implies that, it is impossible to change file,data, and commit message and any other data from the Git database without knowing Git.
####No need of powerful hardware
Developers don't interact with the server unless they need to push or pull changes. All the heavy lifting happends on the client side, so the server hardware can be very simple indeed.
####Easier branching
CVCS used cheap copy mechanism, if we create a new branch, it will copy all the codes to the new branch, so it is time-consuming and not efficient. Also, deleting and merging of branched in CVCS is complicated and time-consuming. But branch management with Git is very simple. It takes only a few seconds to create, delete, and merge branches.
###DVCS terminologies
####Local Repository
Every VCS tool provides a private workplace as a working copy. Developers make change in their private workplace and after commit, these changes become a part of reporsitory. Git takes it one step further by providing them a private copy of the whole repository. User can perform many operations with this repository such as add file, remove file, rename file, move file, commit changes, and many more.
####Working Diretory and Staging Area or Index
The woking diretory is the place where files are checked out. In other CVS, developers generally make modifications and commit their changes directly to the repository. But Git uses a different strategy. Git dones't track each and every modified file. Whenever you do commit an operation, Git looks for the files present in the staging area. Only those files present in the staging area are considered for commit an not all the mofified files.
Let us see the basic workflow of Git.
**Step 1:** You modify a file from the working directory
**Step 2:** You add these files to the staging area.
**Step 3:** You perform commit operation that moves the files from the staging area. After push operation, it stores the changes permanently to the Git repository.
####Blobs
Blob stands for Binary Large Object. Each version of a file is repesented by blob. A blob holds the file data but doesn't contain any metadata about the file. In Git, files are not addressed by names. Everthing is content addressed.
####Trees
Tree is an object, which represents a directory. It holds blobs as well as other sub-directories. A tree is a binary file that stores feferences to blobs and trees which are also named as SHA1 hash of the tree object.
####Commits
Commit holds the current state of the repository. A commit is alse named by SHA1 hash. You can consider a commit object as a node of the linked list. Every commit objett has a pointer to the parent commit object. From a given commit, you can travers back by looking at the parent pointer to view the history of the commit. It a commit has multiple parent commits, then that particular commit has been created by merging two branches.
####Branches
Branches are used to create another line of development. By default, Git has a master branch, which is same as trunk in Subversion. Usually, a branch is created to work on a new feature. Once the feature is completed, it is merged back with the master branch and we delete the branch. Every brank is referenced by HEAD, which points to the latest commit in the branch. Whenever you make a commit, HEAD is updated with the latest commit.
####Tags
Tag assigns a meaningful name with a specific version in the repository. Tags are very similar to branches, but the difference is that tags are immuatable. It means, tag is a branch, which nobody intends to modify.
Once a tag is created for a particular commit, even if you creat a new commit, it will not updated. Usually, developers create tags for product release.
####Clone
Clone operation create the instance of the repository. Clone operation not only check out the working copy, but it also mirrors the complete repository. Users can perform many operationns with this loal repository. The only time networking gets involved is when the repository instances are being synchronized
####Pull
Pull operation copies the changes from a remote repository instance to a local one. The pull operation is used for synchronization between two repository instances.
####Push
Push opertion copies changes from a local repository to a remot one. This is used to store the changes permanently into the Git repository.
####HEAD
HEAD is a pointer, which always points to the latest commit in the branch. Whenever you make a commit, HEAD is update with the latest commit. The heads of the branches are stored in .git/refs/heads/ directory.
###Git Environment Setup

	sudo apt-get install git-core
	yum -y installgit-core

####Customize Git Environment
Git provides the git config tool, which allows you to set configuration variables. Git stores all global configurations in **.gitconfig** file, which is located in your home directory. To set these configuration values as global, add the **--global** option, and if you omit --global option, then your configurations are specific for the current Git repository.

You can alse set up system wide configuration. Git stores these values in the **/etc/gitconfig** file, which contains the configurtion for every user and repository on the system. To set these valus, you must have the root right and use the **--system** option.

#####Setting username
	
	git config --global user.name "woody"

#####Setting email id
This information is userd by Git for each commit
	
	git config --global user.email "1@1.com"

#####Avoid merge commits for pulling
You pull the latest changes from a remote repository, and if these changes are divergent, then by default Git creates merge commits. We can avoid this via following settings.
	
	git config --globla branch.autouprebase always

#####Color highlighting
The following commands enable color highlighting for Git in the console.
	
	git config --global color.ui true
	git config --global color.status auto
	git config --globla color.branch auto

#####Setting default editor
	
	git config --global core.editor vim

#####Setting default merge tool
Git does not provide a default merge tool for ingerating conflicting changes into your working tree. We can set default merge tool by enabling following settings

	git config --global merge.tool vimdiff

#####Listing Git settings

	git config --list

###Git Life Cycle
General workflow is as follows:

- you clone the git repository as a working copy
- you modify the working copy
- if necessary you also update the working copy by taking other developers changes
- you review the changes before commit
- you commit changes. If everything is fine, then you push the changes to the repository
- after commmitting, if you find something is wrong, then you correct the last commit and push the changes to the repository.

### Git Create Operation

####Creat a bare repository

	git --bare init

#### Generate Public/Private RSA key pair

	ssh-keygen

ssh-keygen has generated two keys, first one is private(i.e., id\_rsa) and the second one is pubilc (i.e., id_rsa.put)

#### Adding keys to authorized_keys

add public key to the server by using ssh-copy-id command:
  
	ssh-copy-id -i ~/.ssh/id_rsa.pub gituser@git.server.com

####Push changes to the repository

	git init
	git status -s
	git add .
	git commit -m 'xxxx'
	git log
	git remote add origin gituser@localhost:project.git
	git push origin master

###Git Clone Operation

	git clone gituser@locahost:project.git

###Git Perform Changes

	git cmomit

###Git review changes

    git log
	git show xxxx
	git diff

###Git commmit change

	git commit --amend -m 'xxxxxx'

###Git Push Operation

	git push origin maser

###Git Update operation

	git pull

###Git Stash Operation
Sometimes you cannot commit your partial code and also cannot throw away your changes. So you need some temporary space, where you can store your partial changes and later on commit it.
	
	git stash
	git stash list
	git stash pop

###Git Move Operation
	
	git mv string.c src/

###Git rename operation

    git mv stirng.c stirng_rename.c

###Git delete operation

	git rm file

###Git fix mistake
####Revert uncommitted changes
	
	git checkout file

####Remove change from stage area

    git checkout HEAD -- string_operations.c

#### Move HEAD Pointer with Git Reset

	git log -1
	git reset --soft HEAD~
	git reset --mixed
	git reset --hard xxxx

###Git Tag operation
####Create Git Tag
	git tag -a 'Release_1_0' -m 'xxx' HEAD
	git push oritin tag Release_1_0
#### View Tags
	git tag -l
	git show Release_1_0
#### Delete Tags
	git tag -d Release_1_0
	git push origin :Release_1_0
### Git Patch
    git format-patch -1
    git apply *.patch
    git am *.patch
### Git Managing Branches
	git branch new_branch
	git branch
	git checkout new_branch
	git checkout -b test_branch
	git branch -D test_branch
	git branch -m new_branch wchar_support
	git push origin wchar_support
	git log origin/wchar_support -2
	git merge origin/wchar_support
### Git - Online Repositories

	git remote add origin https://github.com/kangralkar/testing_repo.git

	git push -u origin master

    .git/config
    
	[remote "origin"]
    url = https://woody0907@github.com/woody0907/testing_repo.git



