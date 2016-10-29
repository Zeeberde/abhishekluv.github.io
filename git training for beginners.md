![](http://ipengineer.net/wp-content/uploads/2015/04/git-logo.jpg)

## Git and GitHub Training

This PDF book on Git and GitHub will give you hands-on demo on how to use Git and GitHub practically for any project.

*Last Updated on : 10/29/2016 5:56:09 AM*

*Created by Abhishek Luv* 

*[http://www.abhishekluv.in/](http://www.abhishekluv.in/)*

## Things required for this Training?

- Windows Laptop
- Msysgit.exe 
- Git Extension

## What is Version Control?

What is version control, and why should you care? Version control is a system
that records changes to a file or set of files over time so that you can recall
specific versions later. 

## History of Git

- birth in 2005 by Linus Torvalds
- For Linux kernel maintenance

## Installing Git and Git Extension

- msysgit.exe : Installs Git Software
- git extensions : GUI tool for using Git on PC

![](http://i.imgur.com/byTowlS.png)

![](http://i.imgur.com/s4vMa90.png)

![](http://i.imgur.com/af4ljgU.png)

## What is a repository?

A repository is simply a database containing all the information needed to retain and manage the revisions and history of a project. 

Within a repository, Git maintains two primary data structures, the object store and the index.

The object store is designed to be efficiently copied during a clone operation as part of the mechanism that supports a fully DVCS.

Index is transitory information, is private to a repository and can be created or modified on demand as needed.

## Content-Addressable Names

The Git object store is organized and implemented as a content-addressable storage system. Each object in the object store has a unique name produced by applying SHA1 to the contents of the object, yielding an SHA1 hash value. Any tiny change to a file causes the SHA1 hash to change, causing the new version of the file to be indexed separately.

Git is a content-addressable filesystem. 

*What does that mean?* 

It means that at the core of Git is a simple key-value data store. 

You can insert any kind of content into it, and it will give you back a key that you can use to retrieve the content again at any time.

SHA1 values are 160-bit value that are usually represented as a 40 digit hexadecimal number.

*For example:*
`937082042f48a5cbc7777634509310fff059bc19`


## Understanding what is an Index in Git

The index is a temporary and dynamic binary file that describes the directory structure of the entire repository.

Index captures a version of the project’s overall structure at some moment in time. As a developer, we execute Git commands to stage changes in the index. 

Changes usually add, delete or edit some files or set of files. The index records and retains those changes, keeping them safe until you are ready to commit them. You can also remove or replace changes in the index.

Git’s Index doesn’t contain any file content: it simply tracks what you want to commit when you run git commit. 

Git checks the index rather than your working directory to discover what to commit.

You can query the state of the index at any time with the command  git status

## File Management & Classification in Git

Remote Repository(master) <-> Index(Staging happens here) <-> Local Repository (local)

- Tracked : Any file that’s already there in the repository or any file that is staged
- Ignored : file to be ignored by git object store and git index
- Untracked : An untracked file is any file not found in either of the previous two categories

## Git Internals : The .GIT Directory

**.git Directory**

This is the magic directory where all the git "stuff" is stored. 

**Git Object Store**

You should see a bunch of directories with 2 letter names.The directory names are the first two letters of the sha1 hash of the object stored in git.

It contains your original data files and all the log messages, author information, dates, and other information required to rebuild any revision or
branch of the project.

*There are four types of Object stores:*

- Blobs: A blob holds a file’s data but does not contain any metadata about the file or even its name.
- Trees: Its records blob identifiers, path names and a bit of metadata for all the files in one directory. It can also recursively reference other
subtrees.
- Commits: A commits object holds metadata for each change introduced into the repository, including the author, committer, commit data, and
log message.
- Tags: A tag object assigns an arbitrary human readable name to a specific object usually a commit.

**Config file**

This is a project-specific configuration file. Config entries in here will override the config entries in the .gitconfig file in your home directory, at least for this project.

**Branches and Tags**

You should recognize the files in the tags subdirectory. Each file corresponds to a tag you created with the git tag command earlier. Its content is just the hash of the commit tied to the tag.

The heads directory is similar, but is used for branches rather than tags. We only have one branch at the moment, so all you will see is master in this directory.

**The HEAD File**

The HEAD file contains a reference to the current branch. It should be a reference to master at this point.

## Generating SSH Key for GitHub using Git Extensions

Using GitHub via HTTPS with Git Extensions can become pretty boring. SSH to the resuce. With SSH you wont have to enter the GitHub.com password again an again for every push you make.

**Click on Generate or import key**

![](http://i.imgur.com/V62YvcO.png)

**Click on Generate button**

![](http://i.imgur.com/JwjCACx.png)

**Click on Save Private Key**

![](http://i.imgur.com/EsI9Tmg.png)

**Save the SSH Private key with .ppk extension**

![](http://i.imgur.com/6WfN4mj.png)

**Copy the SSH Key**

![](http://i.imgur.com/n8TfmR2.png)

**Setup the SSH key with GitHub Settings**

- Visit SSH Key settings URL : [https://github.com/settings/keys](https://github.com/settings/keys)
- click New SSH Key
- click Add SSH Key

![](http://i.imgur.com/3PX9Dyc.png)

## Cloning/Downloading an Existing Repository

**Use the Green Clone or Download button**

![](http://i.imgur.com/Ty8WDt4.png)

*copy the SSH Clone URL*

![](http://i.imgur.com/kdX7WmL.png)

**click clone repository**

*steps*

- Set repository SSH clone URL
- Set repository local destination
- folder in which the repository should be cloned

![](http://i.imgur.com/cBRGNlz.png)

**Click Load SSH Key and select the .ppk file and click clone**

![](http://i.imgur.com/w2TGSaP.png)

![](http://i.imgur.com/2fzvEP7.png)

**Click Yes**

![](http://i.imgur.com/AnMUCzI.png)

![](http://i.imgur.com/kuScPTH.png)

## Basic workflow of Version Control

- Creating a local repository
- Cloning an existing remote repository
- Making changes to existing files or creating new files
- Staging : only staged changes are saved in the local repository as a new commit
- Commit : committing changes to the local repository
- Inspecting commit history 
- Sharing via remote repositories.

## Creating a new local repository

**Click on Create New Repository**

![](http://i.imgur.com/NJBsoLi.png)

**Provide a directory folder for your New Repository**

![](http://i.imgur.com/KlF7dh9.png)

**Initialized empty Git repository**

![](http://i.imgur.com/WGdZziH.png)


## Ignoring Files

*Only untracked files can be ignored. You can only ingore files before adding those files in the .gitignore file and also commiting it before adding those untracked files and folders.*

- temporary files
- cache files
- build files
- log files
- password/personal configuration files

**this is how you do it**

- Ignoring all .txt file : *.txt
- Ignoring a single file in a folder : css/general.css
- Ignoring all files in a folder : password/*

![](http://i.imgur.com/mzsdIdz.png)

**Click on Edit .gitignore button**

![](http://i.imgur.com/H7wDxm5.png)

**Click Add default ignores and save**

![](http://i.imgur.com/TRLag71.png)

**Click on Commit button**

![](http://i.imgur.com/oQEfLbR.png)

![](http://i.imgur.com/EhGVcs4.png)

**Click on stage, Write a commit message and Commit**

![](http://i.imgur.com/8fpreOS.png)

![](http://i.imgur.com/mMmtYIV.png)

**.gitignore file added successfully**

![](http://i.imgur.com/4o2teMR.png)


## Inspecting Local Changes

![](http://i.imgur.com/jchZtj4.png)

![](http://i.imgur.com/yT0gg1d.png)

![](http://i.imgur.com/lbuwuV5.png)

## Staging and Committing changes

Working copy -> Staging area(changes for next commit) -> Local Repo (git folder)

- Tracked : modified or unmodified
- Untracked 
- Select the changed you want to stage and commit

*Staged*

![](http://i.imgur.com/HjUEqIl.png)

**Remember this Golden rule of version control**

- Only commit related changes!
- 1 Commit = 1 Topic

## Commit History

![](http://i.imgur.com/bniQGzB.png)

## Introduction to Branches

- Branches are like folders
- branches keep separate topics cleanly separated from each other. topic can be a new feature

**Why use branches?**

- Always keep you new code in a new branch
- By doing that the bugs will be there in that newly create branch and not in your master or current development branch.
- Branches are efficient. No folders, No copies of your project files.
- clear history of changes. Commits in separated context.
- simple integration i.e. merge branches quickly and easily.

**Rules for branches**

- A branch for each new topic/feature
- new features
- experiments
- bugfixes
- or anything else.

You can create and delete new branches or later on merge the new branch features to your current or master branch.

**Understanding Head : The currently active branch**

- At any time, only one branch is active = checked out = HEAD
- You are always working on a branch when using git.
- Checkout command moves the HEAD pointer to a different branch and thereby makes that branch active.
- In the background a couple of things will happen. This is the magic of git internals like index, git object store, blobs, tags and others.

## Creating and Navigating Branches

*Scenario: It's time to do a major rewrite of the whole software. Since this might take awhile, you'll want to put these changes into a separate branch to isolate them from changes in master*

**Creating a Branch**

![](http://i.imgur.com/NvLD2Qb.png)

![](http://i.imgur.com/L34MTkq.png)

![](http://i.imgur.com/CXQSyzm.png)


**Navigating a Branch**

![](http://i.imgur.com/bBOq7uG.png)

![](http://i.imgur.com/NwFFxL3.png)

## Merging Branches

Merging brings the changes in two branches together. Let's go back to the master branch and merge local onto master.

Merging everything from one branch to another branch produce ugly commit graphs. Later we will look at the option of rebasing rather then merging.

*For example: Let's make some changes in a local branch and then merge that change into the master branch*

**Making a change in local branch and committing it locally**

![](http://i.imgur.com/rFKijUq.png)

![](http://i.imgur.com/G1THtxQ.png)

![](http://i.imgur.com/M4vaBvn.png)

**Checkout to master branch**

![](http://i.imgur.com/gnoRriB.png)

**Click on Merge Branches and select merge with local**

![](http://i.imgur.com/tbdsG0r.png)

![](http://i.imgur.com/6lhVv3N.png)

![](http://i.imgur.com/qNxpPgv.png)

**Pushing to origin/master and origin/local**

![](http://i.imgur.com/bIVgIaT.png)

![](http://i.imgur.com/EV6D2Rn.png)

## Creating and Dealing with Merge conflicts

*You can always undo a merge and start over.*
*Conflicts don't bring your team to a halt. They only affect you.*

Dealing with Multiple Branches with different(conflicting) changes.

*While you were changing a branch, someone else decided to update the master branch.*

<<<<< HEAD

====== separates the code line 

'>>>>>>>' Some other branch

The first section is the version on the head of the current branch. The second section is the version on the master branch

You need to manually resolve the conflict and commit the conflict resolution.

*For example: Let's add a sentence "i am a conflict' in the local branch and then commit it. Next checkout to master branch and add a sentence "i am a very big conflict". Some conflict will come up. Let's solve them.*

**Adding sentence in local branch**

![](http://i.imgur.com/wY8yk9P.png)

**Checkout to master branch and add a sentence**

![](http://i.imgur.com/ILgfnSW.png)

**Now let's try to merge local in master branch**

![](http://i.imgur.com/z7eZywL.png)

![](http://i.imgur.com/NCa7RK7.png)

![](http://i.imgur.com/LWB5PK4.png)

![](http://i.imgur.com/Ex1niTt.png)

![](http://i.imgur.com/gjHNdKk.png)

![](http://i.imgur.com/5TrikIA.png)

## Rebasing vs Merging

Use the rebase command rather than the merge command.

We want to get the changes in local into our master branch.

This time we will use the rebase command instead of the merge command to bring in the changes from the local branch.

*Go in master branch -> click rebase and Click rebase*

The final result of the rebase is very similar to the merge. The local branch now contains all of its changes, as well as the changes from the master branch. The chain of commits are linear and much easier to read.

Don't use rebase... If the branch is public and shared with others. Rewriting publicly shared branches will tend to screw up other members of the team.

*Use rebase for short-lived,local branches and merge for branches in the public repository*


## Undoing things using Git

**fixing your last commit**

- wrong commit message or forgotten changes
- the very last commit can be easily fixed in Git
- Reverting commit : easy
- Reset command : Resetting the HEAD

*click revert commit*

![](http://i.imgur.com/nzUFvFO.png)

*check the checkbox Automatically create a commit*

![](http://i.imgur.com/6L02cnv.png)

![](http://i.imgur.com/qVijMvX.png)

*checkout to master branch*

![](http://i.imgur.com/tMd8y1K.png)

![](http://i.imgur.com/0HtyZ3J.png)

## Stash Saving changes temporarily

Saving changes temporarily without committing

Never commit hald-done work. Never ever.

Stash is like a clipboard. Just click apply stash.

**When to use the Stash?**

- Before checking out a different branch
- Before pulling remote changes
- Before merging or rebasing a branch

![](http://i.imgur.com/7LrK3W4.png)

![](http://i.imgur.com/QF53yxZ.png)

![](http://i.imgur.com/EdWH2et.png)

*Working directory is clean*

![](http://i.imgur.com/p5fSt0U.png)

*How to get the stash file content back?*

- click on stash changes
- select a stash file
- click Apply Selected

![](http://i.imgur.com/P7yyBv1.png)

![](http://i.imgur.com/z0yUjNO.png)

## Tags

- Allow you to make important points in your projects history
- for example release 1.0
- Tags are not pushed. We need to explicitly push the tags to the remote repository

*Click Create Tag*

![](http://i.imgur.com/kvwEt0E.png)

*Creating and Pushing a Tag*

![](http://i.imgur.com/EDDi3o4.png)

![](http://i.imgur.com/G3IP7H8.png)

![](http://i.imgur.com/pRB385x.png)

## Remote Repositories

**Remote Branch**

You should see a master branch in the commit history list. But you will also have number of strangely named branches [origin/master, origin/local]

## Connecting a Remote Repository

- Cloning from a Remote : github and git will setup the clone,push and pull urls. When cloning, Git saves the cloned remote as origin. origin is a naming convention
- Adding a remote connection
	- create a empty local repository
	- and connect it with your remote repository

*Create a Local Repository*

![](http://i.imgur.com/vXcXlix.png)

![](http://i.imgur.com/T3HSLWp.png)

*Create a Remote Repository*

![](http://i.imgur.com/onDiDws.png)

*Copy SSH Url*

![](http://i.imgur.com/nmVzQhp.png)

*Click Command -> Push*

![](http://i.imgur.com/TZfXwHs.png)

*Click Manage Remotes*

![](http://i.imgur.com/cIONMd6.png)

**What is Origin?**

Anything within an "origin" word is a remote repository. Remote repositories typically live on a separate machine, possibly a centralized server. 

*Adding remote repository as an origin*

![](http://i.imgur.com/xaZtGvw.png)

*Load SSH Key and Click Test Connection and click Save and Close*

![](http://i.imgur.com/QfWnpPC.png)

*Click Yes*

![](http://i.imgur.com/bffxW1t.png)

*Success*

![](http://i.imgur.com/zBBi3S0.png)

**Local vs Remote Branches**

- Git has all the commits from the original repository, but branches in the remote repository are not treated as local branches here. If we want our own local branch, we need to create it ourselves.

## Sharing data on a Remote Repository

- Both local and remote repos are independent from each other.
- Tracking connections : with tracking feature github will tell you the local branch is ahead of its remote counterpart.

## Publishing a local repo on a remote server

**pushing changes to a remote repository**

- HEAD is pushed. You always push the current local HEAD branch.
- If any issues. First pull the latest commits and then push again.

![](http://i.imgur.com/Tuzj7de.png)

![](http://i.imgur.com/FWcQNAx.png)

Tracking : tracking established between local and remote repo.

![](http://i.imgur.com/9zF1UNX.png)

![](http://i.imgur.com/Z0t4dnl.png)

![](http://i.imgur.com/CbwmoBt.png)

## Pulling and fetching remote changes

- download : pull(integrate new commits in your working folder) and fetch(doesn't integrate new commits in your working folder)
- fetch : downloads new data from the remote but it allows you to integrate what you want to.
- pull : downloads new data and integrates/merges it into your HEAD branch. pull = fetch and merge command

*For example: Let's make an edit using github.com and then pull those new changes in our local repository using the Pull button*

*Click Create New File*

![](http://i.imgur.com/CbwmoBt.png)

![](http://i.imgur.com/hh5dl6M.png)

*Now let's pull the newly created .txt file*

Click Commands -> Pull

![](http://i.imgur.com/iXbe52L.png)

![](http://i.imgur.com/sZz9kIY.png)

![](http://i.imgur.com/cRcoAVH.png)

## Branching workflows

**types of branches**

*create a branch for every topic. Each topic(feature,bugfix,experiment) should get its own branch*

- short-lived branches : have a short life span
- Long running branches : independent of individual topics. they represent state in your project lifecycle like production, testing, development.
	- rules :
	- dont perform commits on these branches
	- master : should contain only production-quality code
	- develop : integrate code these short-lived branches in the master branch after testing.
- master branch :
	- no direct commits
	- commits only through integrations/merges from other short-lived branches.
	- features are developed in new (short-lived) branches.
	- after the feature is developed. the develop branch should be merge back into master branch.
	- integrate as often as possible. if you integrate/merge after two week you'll have a lot of merge conflicts. So always integrate/merge as often as possible.

## Creating a Fork

A fork is a copy of a repository. Forking a repository allows you to freely experiment with changes without affecting the original project.

Most commonly, forks are used to either propose changes to someone else's project or to use someone else's project as a starting point for your own idea.

A great example of using forks to propose changes is for bug fixes. Rather than logging an issue for a bug you've found, you can:

- Fork the repository.
- Make the fix.
- Submit a pull request to the project owner.

If the project owner likes your work, they might pull your fix into the original repository!

**Development Workflow for Fork and Pull Request**

- Fork a Repository
- Clone it locally on your PC
- Create a new branch (New Feature)
- Make changes and commits
- Create a pull request
- The admin of the Main repository will merge your pull request if he likes your work

For example: I want to propose some changes to this repository

*Create a Fork of this Repository, Click on Fork*

https://github.com/abhishekluv/Develop2Deploy.OpenGraph

![](http://i.imgur.com/ZIASX6g.png)

*This forked repo is my personal copy*

![](http://i.imgur.com/vbRzpbX.png)

*Let's clone this forked repo*

![](http://i.imgur.com/36EdQQH.png)

![](http://i.imgur.com/grwlETR.png)

*Adding a new file*

![](http://i.imgur.com/jWBNp9V.png)

![](http://i.imgur.com/JoD9yOc.png)

## Understanding Pull Requests

Pull requests let you tell others about changes you've pushed to a GitHub repository. Once a pull request is sent, interested parties can review the set of changes, discuss potential modifications, and even push follow-up commits if necessary.

## Creating a Pull Request

![](http://i.imgur.com/TEtxw3n.png)

*Click Create pull request*

![](http://i.imgur.com/s4edRG1.png)

![](http://i.imgur.com/2jEKYhc.png)

![](http://i.imgur.com/aWCKaGh.png)

## Accepting and Merging Pull Requests

![](http://i.imgur.com/QgZzjmA.png)

![](http://i.imgur.com/J9vErAE.png)

*Click Merge pull request*

![](http://i.imgur.com/OGvjBFH.png)

![](http://i.imgur.com/6MHehPS.png)

## Best Development Workflow with Git 

- Forking a Repository
- Branching
- Committing
- Creaing a Pull Request
- Merging Pull Request

**Detailed Steps**

- Fork a repository, for example : https://github.com/abhishekluv/Develop2Deploy.OpenGraph
- Clone this project to your local machine
- Create a branch for new changes/features, for example : my-latest-feature
- Develop on my-latest-feature branch only, But do not merge my-latest-feature branch to the master branch as it should stay equal to upstream master branch.
- Commit changes to your my-latest-feature branch
- Push your my-latest-feature branch to GitHub, to allow your mentor to review your code.
- He will merge your pull request
- Delete the my-latest-feature branch locally and remotely
- Now Pull the latest changes from the master branch of the original repo to your forked clone copy. By doing this both the master branch stay equal and clean to work with.

**Demo**

*Creating local branch, making changes and pushing changes to github*

![](http://i.imgur.com/AHpjxwD.png)

*Creating a new pull request*

Creating a new pull request to master branch from local branch of the forked cloned repository.

![](http://i.imgur.com/S7ZSJgz.png)

![](http://i.imgur.com/WPSn3ev.png)

![](http://i.imgur.com/aQgpkov.png)

*Merging pull request in master branch*

![](http://i.imgur.com/6W0AdeP.png)

![](http://i.imgur.com/EjGARPx.png)

*Delete the local branch locally and remotely and pull new changes to the master branch of the forked clone repository by creating a pull request*


![](http://i.imgur.com/W8kGjXl.png)

*Click try switching the base*

![](http://i.imgur.com/Ygdtlc1.png)

![](http://i.imgur.com/cKzo8gH.png)

*Click Merge Pull request*

![](http://i.imgur.com/03xJtpL.png)

![](http://i.imgur.com/s3g0YcN.png)

*Let solve a problem*

https://help.github.com/articles/configuring-a-remote-for-a-fork/

https://help.github.com/articles/syncing-a-fork/

![](http://i.imgur.com/GM6qReH.png)

![](http://i.imgur.com/QwFKdXI.png)

*Crearing a PR*

![](http://i.imgur.com/5DpcEYZ.png)

![](http://i.imgur.com/Ylu7eFc.png)

![](http://i.imgur.com/igllgV2.png)

*Delete Local branch and adding a new remote URL*

![](http://i.imgur.com/VsfVDkH.png)

*Now pull changes from the upstream branch to the forked master branch*

![](http://i.imgur.com/8kdnveT.png)

*Now push the latest pulled changes to your forked master branch*

![](http://i.imgur.com/vdQ5BS7.png)

Thank You!

Regards

Abhishek Luv