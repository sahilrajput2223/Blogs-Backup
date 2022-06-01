## Getting Started with Git

Hello World !

Almost all developer now using [Version Control](https://en.wikipedia.org/wiki/Version_control)  to manage there source code.


> Version control, also known as source control, is the practice of tracking and managing changes to software code.

### Benefits of using version control 

- it manages a collection of changing and improving files.

- complete history of project is tracked and available at any time.

- helpful to collaborate in same project for all team members.

- we can also easily test, fix or undo ideas and changes.

To get started with version control, you need to download and install git in your system. you can download git from  [this link](https://git-scm.com/).

### Git

Git is  [Distributed Version Control System](https://en.wikipedia.org/wiki/Distributed_version_control) .

> Distributed Version Control System is a type of version control where the complete source code (codebase) including its full version history is available on every developer's computer.

#### There is mainly three characteristics of DVCS(Distributed Version Control System)

1. Each user has a local project history (repository).
2. User can work offline. 
3. Can easily synchronize repository. 

#### Before getting started with git, there is some terminologies that we need to understand.

- **Repository(Repo)** : A repository is a directory which contains your project work, as well as a few files which are used to communicate with Git. Repositories can exist either locally on your computer or as a remote copy on another computer.

- **Local repository** : Local repository contains all of the commits that have been made for the projects in offline.

- **Remote repository** : Remote repository usually located in a data center or cloud. This repo also contains all the commits of the project but in case of remote repo, commits are in online mode. This repo considered as a source of truth or official state of project. 

- **Commits** : A repository is made from commits. During commit, we save our project files or codes on particular moments and push to the repo. It's like checkpoint in gaming, which we can visit any time. Also, commits represents the version history of the project.

- **Working Directory** : The Working Directory is the files that we see in our computer's file system.

- **Staging area/index** : files that are planned for next commit.
 
- **Checkout** : A checkout is when content in the repository has been copied to the Working Directory according to branch.

- **Branch** : It's a new line of development, which is completely separate from main line of development.

This are some basic terms we should know before getting started with git.

Once, you download git and installed in your system you can open git bash terminal (which shows in below image)


![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1620706500013/rf4LpRcu4.png)
 

Now, to use git we are going to use some commands. Which is helpful to configure git details, also maintaining repos, creating commits, push and pull source code etc.

**git --version** : we can use this command to verify git version. for ex: `git --version`

![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1620711177322/awQ_O4rWT.png)

**git help cmd** : we can use this command to get help for particular command in our default browser. for ex: `git help push`

![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1620711275558/z3UcLsbi4.png)

**git cmd -h** : we can use this command to get help for particular command in cmd (terminal). for ex: `git  push -h`
 

![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1620711353595/djvi_BNMz.png)

**git config --global user.name "YOUR NAME"** : we can use this command to set default global username in our system which is going to display as author username in every commit. for ex: `git config --global user.name "Sahil Rajput"` 

**git config --global user.email "YOUR EMAIL"** : we can use this command to set default global email in our system which is going to display as author email in every commit. for ex: `git config --global user.email "rajputsahil.2204@gmail.com"`    

**git config user.name** : we can use this command to see username for our system. for ex: `git config user.name` 

![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1620711487615/gL5TIz6sk.png)

**git config user.email** : we can use this command to see email for our system. for ex: `git config user.email` 


![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1620711638876/FucRBuvOj.png)

#### Now, let's get started with one example and learn about some more commands in git.

For this example, I'm going to use one of my git repo Located on  [this link](https://github.com/sahilrajput2223/git-test). 

**Note:** If you don't have GitHub account, then you can create from  [this link](http://github.com/) .

### **git clone**
Using this command we can clone (make copy) of our remote repo in our system as a local repo.
   for ex: `git clone https://github.com/sahilrajput2223/git-test.git`

![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1620710978374/4xQ49XwBC.png)

We can get clone URL from remote repo as shown in above image.

To clone remote repo into our system, we are going to use git clone command as shown in below image.

![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1620712124863/lpr12Rvhw.png)


Now, you can check that whole working tree (file structure) for that remote repo is created in your system. 

Now, let's create one basic notepad file named `HelloWorld.txt` and add that file in that local repo.

### **git status**

Once, the file is created and added in local repo(working tree) we can use git status command to check the status of our repo files.

- if we create new files and add it in working tree, then we can see the status of that files as a `untracked files` as shown in below image.
    
![c.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1620712644195/jJkBnizbn.png)
 
- if we delete files from working tree, then we can see the status of that files as `deleted` as shown in below image.

![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1620712786617/wyTnRES5V.png)

- if we added our new file in staging area, than we can see the status of that files as `new file` as shown in below image.


![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1620712934497/9MfV94BCJ.png)
 
- if we modify our file which is already added in staging area, then we can see the status of that files as `modified` as shown in below image.

![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1620713165880/xjeDr31VX.png)

Also we can use `git status` command as a `git status -s`. which shows us the result in short form.


### **git add**

This command is used to add files and folders in staging area from working tree. We can use this command as `git add <folder/file name>` or `git add .`. 

**git add folder/file_name** : this is useful when we want to add particular file/folder in staging area. we can use this command as shown in below image.

![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1620713456552/LjSBd9nFf.png)

**git add .** : this is useful when we want to add all the files/folders in staging area. we can use this command as shown in below image.

![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1620713587812/tvNpqzizw.png)

Files and folders which are added in staging area/index is going to be add in our next commit.


### **git commit**

We can use this command to add all the files/folders from staging area to local repo as a commit.

This command is used as `git commit -m "COMMIT MESSAGE"`

here, `-m` flag is used to add commit massage. If we don't use this flag then default IDE will open and we need to add commit message over there. 

![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1620714357923/rpJZWxuuR.png)

As shown in above image, we can commit our `HelloWorld.txt` file to local repo and commit message for this commit is `HelloWorld File added`.

### **git push**

We can use this command to commits from local repository to remote repository.

This command is used as `git push <repo> <branch name>` as shown in below image.


![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1620715322850/V86gsS5IW.png)

here, origin is used to store remote repo URL and branch name can be anything that we have created or by default branch name (master/main).

### **git remote**

We can use this command to get information of remote repo.

This command is used as `git remote` or `git remote -v`.

**git remote** : with the help of this command, we can see the shorthand name for the remote repository that a project was originally cloned from.

![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1620716033130/chtLGYHU_.png)

**git remote -v** : with the help of this command, we can see the shorthand name for the remote repository with original remote repo clone URL.


![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1620716277234/8UD1vwej_.png)


### **git pull**

We can use this command to pull all remote repo content into local repo.

Whenever multiple contributors pushing content on remote repo then we need to pull all that content in local repo. So our local repo and remote repo is work in synchronized manner.

- if there is no new commit in remote repo and our local repo is synchronized with remote repo then we can see the output as shown in below image.

![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1620716704525/D3e0ZRqZh.png)
  
- if there is some new commit in remote repo and our local repo is not synchronized with remote repo then we can see the output as shown in below image.

![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1620716901577/nKIGB5W7i.png)


### **git branch**

We can use this command to view all branch which is available in our repo. Also currently active branch noted with `*` sign.
 
![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1620720012530/wsDAv24Uj.png)

Right now, there is only one branch(master) available in this repo.

We can use this command as `git branch <BRANCH NAME>`.

![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1620720247553/o7wM8th1i.png)

As mentioned in above image, we have created new branch called `development`. We can check that by displaying all branches in repo.

![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1620720370562/JXJrlSniQ.png)

Now, in above image you can see there is two branch available `master` and `development`. Also you can see that master branch is noted with `*`, because master branch is active branch.

### **git checkout <BRANCH NAME>**

We can use this command to change our active branch. Once we will change our active branch, according to that branch our working tree content is also updated.

Remember, we have created `development` branch, let's make that branch as our active branch.

![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1620720753485/C7R_9eSsQ.png)

Now, If we use `git branch` then we can see that our active branch is `development` and `*` is moved to development branch. you can see this in below mention image.

![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1620721063606/x5tfFXxQ9.png)

We can also use this command as `git checkout -b <BRANCH NAME>`, you can see this in below mention image.

![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1620721201263/aQaTClJWI.png)

here, `-b` flag is used to create new branch and because of this using only this one command `git checkout -b <BRANCH NAME>` we can create new branch and immediately make it as a active branch. Using this we have `created testing branch and make it as active branch`. 


### **git log**

We can use this command to see commit log history.

We can use this command as `git log`, `git log --oneline`, `git log -n` and `git log --oneline -n`.

- If we use as `git log` then, as shown in below image we can see all commit logs with all details.

![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1620738292735/y7C19CybH.png)

- If we use as `git log --oneline` then, as shown in below image we can see all commit logs as just oneline value.

![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1620738432457/6PzKDsWht.png)

- If we use as `git log -n` then, as shown in below image we can see commit logs with details, but for last n commits only.

![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1620738564257/akF5TV7LD.png)

- If we use as `git log --oneline -n` then, as shown in below image we can see commit logs as just oneline value, but for just last n commits only.


![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1620738738064/7AK1b_0Kc.png)


**Note that**, I have used simple one or two files to show all the examples with git commands, but we can also use this for as many files and folders we want to use.

Also,  If you create new repo in GitHub then `branch name is main` not master.


<br>

Thank you for reading, You can connect me on  [Twitter ](https://twitter.com/Its_SR__) /  [LinkedIn ](https://www.linkedin.com/in/rajputsahil/) /  [Github ](https://github.com/sahilrajput2223) .

