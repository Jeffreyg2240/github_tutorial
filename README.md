# GitHub Tutorial

_by Jeffrey Guan_

---
## [Git vs. GitHub](https://docs.google.com/presentation/d/1b777MzxqxIpTITSXiPOdn9427Oo7VclwecAiZ-5boy8/edit#slide=id.ge18f0c268_0_15)
[Git](https://git-scm.com/docs) is a **verison control** system that keeps track of all the verisons(saves) in a file, and helps manange and organizes it.  

[Github](https://github.com/) is where you store all your files on a cloud, into a remote server, where it keeps track of the file, and allows anyone else to view and copy your file.

Git is used to help move files into or out of Github. Git tracks file verisons and files of all the changes you have mad overtime, while Github is just a open storage space for many different lamguauges of code.

---
## Initial Setup
1. First open your Github
1. Then click on your icon in the top right, make sure you see the drop down menu
![hi](https://github.com/Jeffreyg2240/github-tutorial/blob/master/Screen%20Shot%202017-10-19%20at%201.11.56%20PM.png)
1. Click on settings
1. Once in settings click on SSH and GPG keys.
1. Click on new SSH key  
![hi](https://github.com/Jeffreyg2240/github-tutorial/blob/master/Screen%20Shot%202017-10-19%20at%201.11.33%20PM.png)

![hi](https://github.com/Jeffreyg2240/github-tutorial/blob/master/Screen%20Shot%202017-10-19%20at%201.12.18%20PM.png)
1. Name it "** c9 - 'Name' "  ***(Dont close the page)***
1. Now open your _**c9**_ and log in
2. Click on the gear icon in the top right
2. Click on SSH Keys and copy and the 2nd SSH key on the bottom "Connect to your private git repository Add this key to authorized keys list on your code hosting service (gitlab/github/bitbucket etc.)"
![hi](https://github.com/Jeffreyg2240/github-tutorial/blob/master/Screen%20Shot%202017-10-19%20at%201.21.32%20PM.png)
3. Paste it to your key section in the Github page that you still have open.

#### Congrats your are done setting up your SSH key, and are ready to link and push to Github!
Open your [c9](https://c9.io/) and do as **this** page says to create a new repository.  
![hi](https://github.com/Jeffreyg2240/github-tutorial/blob/master/Screen%20Shot%202017-10-19%20at%201.25.36%20PM.png)

---
## Repository Setup
* "**Git init**" stands for git initize. It helps initize the folder/repository so that other git commands, like "**git add**", "git commit**", and "**git remote**".  
* There are 3 parts to the git project, working directory, staging area, and repository.  
![hi](https://github.com/Jeffreyg2240/github-tutorial/blob/master/Screen%20Shot%202017-10-20%20at%201.00.39%20PM.png)
* The working directory is where you will type the codes.  
* The staging area is where you will prepare all the files to send them to the repository/cloud in Github.  
* You add codes to the staging area with "**git add**".  
* Once the desired files are added, you do "**git commit -m 'message'**" afterwards, then the files is commited and saved. 
* "**Git commit -m 'message'**" creates a verion of the git file and you can rollback to it if anything unexpected happens to the current verison.

```html
jeffreyg2240:~/workspace/github-tutorial (master) $ git commit -m "Commit example"
[master d319951] Commit example
 1 file changed, 12 insertions(+), 12 deletions(-)
```
Additionally if you want to "**git push**" it to github, you need to link the SSH and create a github repository with the same name as the c9 file.
#### Also "**rm -rf .git**" removes git from a file, _**BUT**_ if you "**git init**" in a branch that comes before it, "**rm -rf .git**" would not remove git from the current file you are in.

In order to fix this you would need to "cd .." into which ever file you first "**git init**" in and remove git with "**rm -rf .git**" on that branch.

```html
jeffreyg2240:~/workspace $ git init
Initialized empty Git repository in /home/ubuntu/workspace/.git/
jeffreyg2240:~/workspace (master) $ cd github-tutorial
jeffreyg2240:~/workspace/github-tutorial (master) $ rm -rf .git
jeffreyg2240:~/workspace/github-tutorial (master) $ cd ..
jeffreyg2240:~/workspace (master) $ rm -rf .git
jeffreyg2240:~/workspace $ cd github-tutorial
jeffreyg2240:~/workspace/github-tutorial $ 
```
---
## [Workflow & Commands](https://docs.google.com/presentation/d/1b777MzxqxIpTITSXiPOdn9427Oo7VclwecAiZ-5boy8/edit#slide=id.ge18f0c268_0_31)

"**Git status**" checks all the changes so made so far on your cloud, and if you have "added them".  
```html
jeffreyg2240:~/workspace/github-tutorial (master) $ git status
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
```

"**Git add**" adds the file into the staging area to be commited.  
* "**Git add --all**" adds unadded files to the staging area.
```
$ git add --all
```
* "**Git add 'name'**" adds the a un-added file to the staging area, you choose which file.
```
$ git add "README.MD"
```
* "**Git add .**" adds the current file you are in into the staging area.  
``` 
$ git add .
```
"**Git commit -m 'message'**", moves the staging area to repository, and it creates a verison that you can rollback to later. The message you leave on "git commit" is a self reminder of what you last were working on, or a note to self.
```
$ git commit -m "added a explaination of git commit"
```
  ["**Git remote add origin URL**"](https://docs.google.com/presentation/d/1DcOm1hZQTgsJYxqCE5na8zEAhlyh_Z0V4ivtt8aAsf0/edit#slide=id.g3ad02a1f9_010), connects your current project file to a repository on c9.
* remote sets up an connection between github and your c9 account.
* **add**, adds a new bridge.
* _origin_, can be any name, origin is just a name for the bridge, remote you are making, it can be renamed to anything.
* _URL_, you this this from your github everytime you make a new repository, copy the SSH, URL and paste it in place of the "**URL**"
["**Git push -u origin master**"](https://docs.google.com/presentation/d/1DcOm1hZQTgsJYxqCE5na8zEAhlyh_Z0V4ivtt8aAsf0/edit#slide=id.ge239e83e1_0_10) 
* **Push**, pushes the project to github, but it requires a bridge and direction to which branch.
* **-u** helps remember which branch and repo you last pushed it to, so you can just type "**git push**" next time
* _origin_, must be the same name you named the bridge, remote, in "**Git remote add origin URL**".
* **master**, the _**default** main branch_, unless manually changed.

Afterwards you can type "**git remote -v**" to check where your c9 is connected to in github.
```html
jeffreyg2240:~/workspace/github-tutorial (master) $ git remote -v
origin  git@github.com:Jeffreyg2240/github-tutorial.git (fetch)
origin  git@github.com:Jeffreyg2240/github-tutorial.git (push)
```
---
## [Rolling Back Changes](https://docs.google.com/presentation/d/1yBhhaSNtHEC4Sqc-jMxeMMqPeNOT7zVuiOU_e5eWV_8/edit#slide=id.g25a990f774_1_10)

[Rollback](https://docs.google.com/presentation/d/1yBhhaSNtHEC4Sqc-jMxeMMqPeNOT7zVuiOU_e5eWV_8/edit#slide=id.g192aa2692a_0_0) is a way to undo what you previously did.  
You can rollback to your previous **edit**,  "**git add**", "**git commit**", and "**git push**".
* "**Git checkout --filename**", it reverts to last time the file was added to stage
* "**Git reset HEAD filename**", it removes a file from stage.
* "**Git reset HEAD~1**", it removes takes 2 steps back from the repository to moves the working directory.
* "**Git reset --soft HEAD~1**", deletes the changes of the previous commit, and puts it the staging area.  
* "**Git reset --hard HEAD~1**", deletes all changes and goes back to previous commit.  
![hi](https://i.stack.imgur.com/qRAte.jpg)
* "**Git log**", it shows you all the previous commits and the notes you added with it, you can copy the code each commits give and rollback to it.
**NOTE YOU CLICK "Q" TO EXIT**
![hi](https://ffcb9532-a-cd86e757-s-sites.googlegroups.com/a/hstat.org/jeffreyg2240sep11/github/githubtutorial/Screen%20Shot%202017-10-25%20at%201.06.07%20PM.png?attachauth=ANoY7crB0M7UAmGyvjcc9ldI97c-l9SAsdkOIkSWXU5b-n5DAXTVX99hRP-1gcjOqL9Mi-MDnUPJIiDsVYtVGBI-aRqEl1QRot9CoUj8J6OB16FolOqQF49e7f4bp7m9wGwK0hGzxVxS6ZoFBPnHAEisoJ_fdCkjbtPRRVCAh0_3gn5iI7FXzt07vN0vzNK8YWE0ksUvNaSu5RHu-qt48zloFKzGBy9b7p5RaqLT7f8doCmntxYbHoFt4iK_19ASnfYi_CRlHHMdsOkqYZUtbmtNE8bipYFWGg%3D%3D&attredirects=0)  
* ["**Git reset HARD --''**"](https://docs.google.com/presentation/d/1yBhhaSNtHEC4Sqc-jMxeMMqPeNOT7zVuiOU_e5eWV_8/edit#slide=id.g25a990f774_1_4) Sets it back to a specific time depending on which "**git log**" code you choose.

---
## Collaboration
* "**Git remote remove**", removes the connection to the remote file, github in this case.
* "**Git remote -v**", this commands checks what remote your project is currently connected to.
![hi](https://github.com/Jeffreyg2240/github-tutorial/blob/master/Capture.JPG)
* "**Git clone 'URL'**", it creates a copy of the repository to your local server.
The URL is the SSH code from every time you create a new repository in github.
![hi](https://github.com/Jeffreyg2240/github-tutorial/blob/master/Capture11.JPG)

When you fork a file, you are basically cloning a file, but the owner of the project will still be from the cloud you forked it from.  
Forking a project allows for you to sumbit "**pull requests**", which allows the owner of the project to see what changes you made in his/her project,  
and allows him/her to **merge** your verison of the file to his/her. Merging is replacing their project with the one you sumbitted.  
To [fork](https://docs.google.com/presentation/d/1DU_Q9CJZ2_KHue4MnfKmd0sJWMowp94OAIfQceluosY/edit#slide=id.ge40aa0d51_0_47) a project you would need to do basically what you did to clone the project with a few more steps.
![hi](https://github.com/Jeffreyg2240/github-tutorial/blob/master/Capture4.JPG)
You click on fork, and fork the project, then you copy the SSH of the forked project and clone it.  
To sumbit a "**pull request**", you click on Pull requests, then "**New pull request**", and finally click on "**Create pull request**" once you are done with your message to the owner.  
![hi](https://github.com/Jeffreyg2240/github-tutorial/blob/master/Capture2.JPG)
![hi](https://github.com/Jeffreyg2240/github-tutorial/blob/master/Capture3.JPG)