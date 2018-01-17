# Git & Github collaboration tutorial

lab meeting 18.01.2018 @ Ghent

---
# Plan



<img src="images/git.png" alt="https://xkcd.com/1597/" width="whatever" height="300">

- what is version control
- git & github 101
- git workflow
- collaboration possibilities
- and moar

---
# Version control

Management of **changes**, called **revisions** to any types of information

- Simple file versioning  
  - add v1.0, v1.1, …  to filenames
![](https://d2mxuefqeaa7sj.cloudfront.net/s_73A0E937615C98AD21B1CCD0B08D38E1017413FC2A8DCA0E44FD2BDC65497CF1_1516195377774_phd101212s.gif)
![](https://lh6.googleusercontent.com/wnQri7PocE90x0z47oB3F6BmA02yT9W2tZ4lE52HL7KYUgNC9vfbspi0-oeuIpDLaNbti-L-qmqeKWlIVf0J7Bj_XCVPTUtUNNbNz4fxzNqmR5LLE1Wi94p5nelFh3bTcWORoIxpZnM)

- Simple tools: Google Drive, Dropbox...
- Advanced tools: subversion, mercurial  and git

**Revision:** Change associated with a **timestamp** and the **person** making the change

**Benefits:**

- Go back to previous versions
- Store history of changes
- Collaborate with others


# Git vs Github

**Git**   is a program, allows groups of people to work on the same documents at the same time, and without stepping on each other's toes.”

**GitHub** is an online service

- hosts your repositories (projects)
- helps you work with contributors/collaborators
- web interface for version control
- synchronise among several computers

**Interfaces to GitHub**

- **directly online**
- **with the Github Desktop App**
- via the command line using ‘git’


# Github interface
![](https://d2mxuefqeaa7sj.cloudfront.net/s_73A0E937615C98AD21B1CCD0B08D38E1017413FC2A8DCA0E44FD2BDC65497CF1_1516196260449_image.png)


https://github.com/compneuro-da/Pipeline_GSR_DCM

# Register & set up git on your computer
- Unlimited public repositories https://github.com/join
- When you are academic, you could get private repo for free https://education.github.com/pack
-  join also  lab account @compneuro-da

# Installing git locally
- command line git already installed on ubuntu (if not easy, it is in standard repositories)
	`#sudo  apt-get install git`

- many graphical interfaces guis, there is [github desktop](https://github.com/shiftkey/desktop)
 unoficial fork for linux, also [free pro version for one year for academics](https://www.gitkraken.com/github-student-developer-pack)[gitkraken](https://www.gitkraken.com/)


# Cloning repo

first  fork the  repo to your account

- cloning =  getting something from the web


    git clone https://github.com/danieltomasz/git-tutorial.git


- after that you need to change folder (in unix  `cd`  command)
-  feel free to  `clone`  repos,  you cannot break it on GitHub since you do not have `push` rights.
# Creating repo locally
    git init

  Executing this  will create a new `.git` subdirectory in your current working directory. This will also create a new master branch.

    git add .  
    git commit -m "first commit to the repo"


your repo will now have  all files from folder added to the history and will track future updates to the file.
You could exclude some files  and folders by putting them in special  `.gitignore` file  that is checked in at the root of your repository.


# Connecting  to remote repo
    git remote add origin URL  

so in our case (i created) this repo

    git remote add origin https://github.com/user/repo.git

in case you do mistake

    git remote rm origin

in my case

    git remote add origin https://github.com/danieltomasz/git-tutorial.git

after that  check

    git remote -v

  push your  local changes

# Github terms

**Repository (Repo)**
is a virtual storage of your project. It allows you to save versions of your code, which you can access when needed.

**Commit**
saving a version of file(s)
**> git add README.md**
**> git commit -m ‘My first commit’**

**Issues**
to-do list of tasks, bugs and things you wish to accomplish


![](https://d2mxuefqeaa7sj.cloudfront.net/s_73A0E937615C98AD21B1CCD0B08D38E1017413FC2A8DCA0E44FD2BDC65497CF1_1516196591158_image.png)


**Branch**
When working with a centralized workflow the concepts are simple, `master` represented the official history. With each now scope of work, aka feature, the developer is to create a new branch.

![Screen Shot 2016-02-05 at 2.08.15 PM.png](https://lh5.googleusercontent.com/qYV7uWW76pmMH2wjEhlF030V0X0jvuQNHRkIL_z_F_uJj6sayl_jQ5M5jVjun_DNmaeZ1EuE_P4GeGaIzfehD5bflHaosKnZZplVKXh5raYud1qqTxURs4v3_4YISFXg75F5jiVDSyk)



**Pull request**
request to add your changes from a branch back into master ****
**Merge**
act of incorporating new changes (commits) from one branch to another
**Fork**
make a copy of someone else repository

**Clone**
copy a repository onto your local computer
**Download Zip**
download the content of a repository


# Collaborating with GitHub
# Add collaborators

As the **owner** of a repo you:

    1. **add** people as **collaborators**
    2. each collaborator can read/write files in the repo
    3. each collaborator is adding files and other content → making branches → and either directly merging changes in or via pull requests
# Fork + Pull Request

If you don’t own a repo and aren’t an official collaborator:

  1. you will **fork a repo**
  2. work on your forked copy of the repo
  3. in order to get your changes pulled into the original repo → **make a pull request** for the changes you’ve made
  4. the author/owner of the original repo will determine if your changes are cool → and merge them in.
  5. Make friends + Big party!




## Installing git

[https://gist.github.com/derhuerst/1b15ff4652a867391f03](https://gist.github.com/derhuerst/1b15ff4652a867391f03)


    git push origin remote  


    Keeping a fork up to date

    Raw
    ### 1. Clone your fork:

        git clone git@github.com:YOUR-USERNAME/YOUR-FORKED-REPO.git

    ### 2. Add remote from original repository in your forked repository:

        cd into/cloned/fork-repo
        git remote add upstream git://github.com/ORIGINAL-DEV-USERNAME/REPO-YOU-FORKED-FROM.git
        git fetch upstream

    ### 3. Updating your fork from original repo to keep up with their changes:

        git pull upstream master

check remote


    git remote show origin
    git remote -v
    git remote set-url origin https://github.com/USERNAME/REPOSITORY.git



make a new brancj with clear commit history

    git branch fcbrainhack $(echo "commit message" | git commit-tree HEAD^{tree})




# More advanced stuff

**rebase first, then merge**.

- https://dev.to/maxwell_dev/the-git-rebase-introduction-i-wish-id-had
- git branches [https://railsware.com/blog/2014/08/11/git-housekeeping-tutorial-clean-up-outdated-branches-in-local-and-remote-repositories/](https://railsware.com/blog/2014/08/11/git-housekeeping-tutorial-clean-up-outdated-branches-in-local-and-remote-repositories/)
- https://github.com/mockito/mockito/wiki/Using-git-to-prepare-your-PR-to-have-a-clean-history

#cheatsheet

https://gist.github.com/hofmannsven/6814451


[https://gist.github.com/hofmannsven/6814451](https://gist.github.com/hofmannsven/6814451)
https://sethrobertson.github.io/GitFixUm/fixup.html
