---
layout: default
title: "Git(hub) Remote"
author: "Meeta Mistry, Radhika Khetani, Heather Wick"
---

## Learning Objectives
* Sync local and remote versions of a Git repository

## Repositories online (remote)

### Pushing Your Changes to Your Remote Repository

In the last lesson we were only recording our changes locally, but we may want to have these changes be available remotely as well (for collaborating/sharing/backing up). The idea is you keep your local and remote repositories "in sync".

At the end of the last lesson, we took the first step to synchronizing your repository locally and remotely by publishing it to GitHub's servers, but any further changes you make locally through GitHub Desktop will remain local and not appear remotely until they are **push**ed to GitHub's servers. Any time you make local changes, you might notice the right hand tab on the repository bar will say `Push origin`. `Origin` is the default name for your remote repository (it is possible to change the name, but that is beyond the scope of the lesson). Clicking this button will enact a one-way synchronization which will **push** your changes in your repository from your computer to the GitHub website, and populate the *remote* repository on GitHub's servers in the process.

At the end of the last lesson, we saw our repository on our *Repositories* tab on GitHub.com. If you click on your repository, we can now view our changes on our remote at GitHub.com (if you don't want to navigate there by hand, in GitHub Desktop you can go to `Repository` in the menu bar, then select `View on GitHub` and it will automatically open the repository on GitHub.com for you: 

<img src="../img/2.GHD_githubweb_repo.png" width="800" align="center">

Notice that our commit short descriptions are shown here; and that we can see the different commits that we performed.

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
