---
layout: default
title: "Git(hub) Remote"
author: "Bob Freeman, Meeta Mistry, Radhika Khetani, Kathleen Keating"
---

## Learning Objectives
* Sync local and remote versions of a Git repository

## Repositories online (remote)

### Pushing Your Changes to Your Remote Repository

In the last lesson we were only recording our changes locally, but we may want to have these changes be available remotely as well (for collaborating/sharing/backing up). The idea is you keep your local and remote repositories "in sync". 

This is straightforward in GitKraken and you do it by doing a one-way synchronization of your repository to the remote that you linked it to when you first created the repo. This one-way synchronization will **push** your repository from your computer to the GitHub website, and populate the *remote* repository on GitHub's servers in the process.

<img src="../img/2.new-push.png" width="700" align="center">

We can now view our changes on our remote at GitHub.com. If the left pane, our remote is given the name 'origin', which is the default term for the remote repository in Git (note that you can call it whatever you'd like, and you can have more than one remote! But that is beyond the scope of this lesson.) If we then right-mouse click on our 'origin', we can select the pop-up menu option "View origin on GitHub.com":

<img src="../img/2.new-view_origin_on_github.png" width="700" align="center">

Indeed, GitKraken sends us to our web browser and our repository on GitHub.com is displayed:

<img src="../img/2.new-repo_on_github.png" width="700" align="center">

Notice that our commit short descriptions are shown here; and that we can see the different commits -- serial & coordinated -- that we performed.

> You can also have a fully local repository, without a remote "synced" one on GitHub. 
> If you would like to initialize such a repository with this intention pick the "Local Only" option under "Init".

***

**Exercise #2**

Push the changes to the "learning_github" repo (from the previous exercise) to the remote repo on github.com.

***

On Github, you can choose to keep repositories public or make them private; and if they are private, you can choose specific GitHub users with whom you want to share it or collaborate with. For this lesson, we will stick with having a public repository. 

Once your document is online, you can continue to make local changes to your file. But you will have to synchronize your local changes to reflect these changes in the published GitHub repository. GitHub stores changes both locally (on your computer) and remotely (on their servers), and it is important to keep these changes in sync. 

In GitKraken and standard Git workflows, this is accomplished by regular, intentional rounds of **Pull** and **Push**, which both **pulls** in changes from the remote repository, and **pushes** any local changes to the remote repo. You will be learning more about this in the self-learning lesson!

***

* Materials used in these lessons are derived from Daniel van Strien's ["An Introduction to Version Control Using GitHub Desktop,"](http://programminghistorian.org/lessons/getting-started-with-github-desktop), Programming Historian, (17 June 2016). [The Programming Historian ISSN 2397-2068](http://programminghistorian.org/), is released under the [Creative Commons Attribution license](https://creativecommons.org/licenses/by/4.0/) (CC BY 4.0).*

* Materials are also derived from [Software Carpentry instructional material](https://swcarpentry.github.io/git-novice/). These materials are also licensed under the [Creative Commons Attribution license](https://creativecommons.org/licenses/by/4.0/) (CC BY 4.0).*
