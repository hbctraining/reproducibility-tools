---
layout: default
title: "Getting Started with Git using GitHub Desktop"
author: "Meeta Mistry, Heather Wick"
---

## Learning Objectives

* Describe version control
* Implement version control on text file with Git using the GitHub Desktop interface


## Getting Started with Git using a GUI (Graphical User Interface)

Long-time users of Git often use the command-line user interface (CLI), i.e. a Terminal. However, there are several tools that enable novices to use Git with a Graphical User Interface (GUI) (point-and-click) interface. Two examples of GUIs for Git are [GitHub Desktop](https://desktop.github.com/) and [GitKraken](www.gitkraken.com). We will be using the former.

Although there are several advantages to using Git from the command-line interface in the long run, a GUI is a great place to start with learning the basics. 

> **A Note on Terminology**
> 
> One of the trickier aspects of using Git is the associated jargon (`repository`, `add`, `commit`, `pull`, `push`, `remote`, `detached head`). Some of the commands/terms are fairly self-explanatory, others less so, and in this workshop you will encounter both of these. [Here is a glossary of associated terms](https://help.github.com/articles/github-glossary/), however it is best to pick up terminology while learning how to use GitHub.

### Register for a GitHub Account

Since we are going to be using [GitHub](https://github.com/) along with [GitHub Desktop](https://desktop.github.com/) you will need to register for an account on GitHub if we don’t already have one. 

### Install GitHub Desktop

* After you have downloaded and installed GitHub desktop, open the application and click the `Sign in to GitHub.com` button
* A browser window will open up prompting you to authorize a GitHub User. Sign in to Github or click `continue` if you are already signed in. Depending on your browser, you may see a pop-up prompting you to open `Open GitHub Desktop`; if you agree you will see a follow-up message redirecting you back to the GitHub Desktop application
* On GitHub Desketop, you will see a `Configure Git` prompt which will allow you to use your GitHub account name and email address or configure manually. You should select `Use my GitHub account name and email address` which should auto-fill your GitHub name/email, and click `Finish`
* Then you will be directed to a `Let's get started!` prompt. If you already have repositories in your GitHub account, you should see them here. You will also see options to create and clone repositories. At this point, you've configured GitHub Desktop and are ready to start working with a *repository*.


<p>
    <img src="../img/2.GHD_setup1.png" width="700" align="center">
    <em>1. When you open GitHub Desktop, click "Sign in to GitHub.com" </em>
</p>
<p>
    <img src="../img/2.GHD_setup2.png" width="700" align="center">
    <em>2. In your browser, you will be prompted to authorize a GitHub user. Click "Continue" </em>
</p>
<p>
    <img src="../img/2.GHD_setup3.png" width="700" align="center">
    <em>3. On GitHub Desktop, you will see the Configure Git prompt. Select "Use my GitHub account name and email address" </em>
</p>
<p>
    <img src="../img/2.GHD_setup4.png" width="700" align="center">
    <em>4. When yo usee the "Let's get started!" prompt, you are ready to begin! </em>
</p>

## Version Controlling a directory of files

### Creating a Repository

***So, what is a Git repository?***

*"A Git repository is the .git/ folder inside a project (folder). This repository tracks all changes made to files in your project, building a history over time. Meaning, if you delete the .git/ folder, then you delete your project’s history."* 
-adapted from [https://blog.axosoft.com/learning-git-repository/](https://blog.axosoft.com/learning-git-repository/)

Essentially, a (project) folder is chosen to be tracked and a Git repository is initiated within it; this ensure that the contents, and the changes to the contents within that folder will be "watched" by Git.

A few salient features of repositories are listed below:
* A repository can have many files and sub-folders (basically, a normal folder).
* Best practice is to have a separate repository for each project.
* Do not create repositories for folders within a repository (avoid *matryoshka* repositories!).
* The changes made within repository folders are being "watched" by Git as mentioned above, but these changes have to be deliberately added to the repository in order to be version controlled or recorded.
* You can be control the items that Git is "watching". It is best practice to ignore very large datasets, or temp files.

Download the folder we have generated for this session [from here](https://github.com/hbctraining/reproducibility-tools/raw/master/data/example_files.zip), and unzip it in a location of your choosing. We recommend placing it on your Desktop for the duration of this workshop.

### Creating a Folder/Repository, Starting from your Local Machine

There are a number of different ways to add files/folders for Git/GitHub Desktop to track...

**Method 1: In GitHub Desktop, on the `Let's get started!` screen, click `+ Crete a new repository on your Local Drive...`**

**Method 2:** In GitHub Desktop, if you are already past the `Let's get started!` screen, click `Current repository` in the lefthand side of the repository bar, then in the dropdown menu that appears, click `Add` and select `Create New Repository...`

**Method 3:** In GitHub Desktop, click `File` in the Menu Bar, then select `New Repository...`

**Method 4:** You can also add an existing local repository starting with Method 2 or Method 3 but selecting `Add Existing Repository...` or `Add Local Repository` from the respective dropdown menus and providing the local path of the repository

For this tutorial, we will be using **Method 1**

When you create a new local repository, you will be greeted with this prompt:

<p>
    <img src="../img/2.GHD_create_new_repo.png" width="350" align="center">
    <em>Create a New Repository</em>
</p>

Fill in the fields as appropriate:

1. The `Name` of the repository. Keep this to letters, numbers, and underscores; for this class, let's call it "githubdesktop_workshop".
2. Add a `Description` of what this folder/repository will contain.
3. Choose a `Local Path` where the repository will be stored on your computer. For this workshop, let's place the repo on your Desktop
4. If you want, you can Initialize the repository with a README by clicking the box. For now, we will leave this blank
5. If you would like to choose options for `Git Ignore` and `License`, there are options from the dropdown menu. For this workshop, we will select `None` for both.
6. Finally, click the `Create Repository` button.

**!!!SHOULD WE ADD MORE ABOUT WHAT GIT IGNORE AND LICENSE DO?, see https://docs.github.com/en/desktop/overview/creating-your-first-repository-using-github-desktop**

**Note: Make sure you follow all the steps and instructions listed above!**

Voila! You now have your first Git repo!

Your GitHube Desktop screen should now look like this:

<p>
    <img src="../img/2.GHD_layout.png" width="800" align="center">
</p>

### A quick tour of the GitHub Desktop layout
The black bar on the upper part of the screen is called the repository bar, which has 3 sections:

**Current Repository** (left) shows name of the current repository, which is the new repository you just created. If you click here, you'll see a dropdown menu to create and navigate between repositories. 

**Current Branch** (middle) displays the current branch. If you click here, it will let you view and switch to different branches in your repository (these will be visible once you create *pull* requests in your repository) or create a new branch. 

**Publish repository** (right). This option appears because we haven't yet published our repo to the GitHub Server, which we'll do later on in the lesson. This part of the repository bar will change depending on the status of your current branch and repository.

On the left side of the screen you will also see two tabs:

**Changes** will show you changes made to files in your current directory that haven't been committed to your local repository. This tab also hase "Summary" and "Description" text boxes to describe your changes, and and **Commit to BRANCH** button, which will tell you which branch you are committing to.

**History** will show past commits you've made to the current branch of your repository. For now, you'll only see the **Initial commit** from creating the repository. You will also see any changes to files you created during the commit; in our case, we see there is a *README.md* as well as a *.gitattributes* file. Our *.gitignore* and *LICENSE* files would also appear here if we opted to create those during the initial commit. When you click on these files, you can see the *diff* -- only the parts of the file that changed are displayed. For the initial commit, that's all of the file.


> **Note 1:** The folder should also appear on your Desktop! If you can't find your folder, you can click on `Show in Finder` in the "View the files of your repository in Finder" section on the main screen
>
> **Note 2:** files like *.gitattributes* or any files which start with a `.` are hidden files, so they may not be visible in your Finder window by defualt. To view hidden folders in Mac OSX, you can press `Command+Shift+.`

### Committing Changes

Before we continue, we want to highlight a few research data management best practices: organize your files, structure your folder and name files consistently. 

**MODIFY THIS BECAUSE WE WILL HAVE THEM CREATE A MUCH SIMPLER DIRECTORY STRUCTURE WITH LESS FILES**

1. Let's start by creating 5 new directories in the folder (in Finder, outside of Git: `code`, `data`, `docs`, `figures`, and `other`
2. Now, let's move some of the files from the downloaded `example_files` folder into these newly created directories. Please use the image below as a guide to which file goes where. We won't be moving all the files out of the `example_files` folder, the following 3 files will **not be moved** to the new repo - `Pi Formulas...`, `README.md` (since one is already exists in our new repo), and `util_functions.R`.



After all the moving, **WHAT DOES IT LOOK LIKE IN GITHUB DESKTOP?**




These changes have been noted, but this new *version* of the folder is not yet recorded (saved) by Git. A **commit** tells Git that you made some changes which you want to record. Though a **commit** seems similar to saving a file, there are different aims behind ‘committing’ changes compared to saving changes. **Commits** take a snapshot of the file(s) at that point. You can actually record or commit modifications to multiple files/folders at once. i.e. single commit can have multiple updates.  

Committing changes usually happens in 2 stages:
1. `add` or stage one or many modifications incrementally
2. `commit` them with a special commit message to document the type of updates

To include or **add** these files for a commit, we **stage** all the changes by clicking on .....



You also have the option of adding only certain files to the "Staging" area if you wish to make separate commits. ...


To commit changes one **must give a summary of the changes** followed by clicking on the Commit button:



After the commit, SCREENSHOT OF GITHUB DESKTOP?


A useful way to think about commits is as the ‘history’ of your project. Each commit records a development or change made to the documents in your repository; the history of the project can be traced back by looking at all of the commits. 

* Think carefully about when to make commits, since the advantages of version control rely on taking snapshots of your changes regularly.
* Make the commits "atomic", i.e. **commit a few related changes together**; this will help if you have to revert back to a specific version/snapshot. 
* Use meaningful **commit summaries** and **messages**, so that your messages/summaries are independently understandable by your collaborators and your future self.

> **Note about Branches**:
>
> When you commit you will see ‘commit to master’. This refers to the **master** (or **main**) branch. 
> 
> Within a Git repository it is possible to have multiple ‘branches’. These different branches are essentially different (virtual) places in which to work. Often they are used to test new ideas or work on a particular feature without modifying or "contaminating" the master copy (e.g. production version of a webpage). This feature is very useful when collaborating with others. We do not have time to go into this aspect of Version Control in this workshop, but we encourage you to explore it further.

### Changing File Contents and Committing Changes

We're going to make several sets of changes that reflect the flexibility and capability of a version control system. 

Let's open the `README.md` document using our favorite text editor (see note below about text editors) and make this more useful. The information in this document is displayed at the bottom of the main page of your repo when you view it on GitHub (online). The `.md` extension means that this is a text file in ["markdown" format](https://guides.github.com/features/mastering-markdown/), which GitHub automatically renders into readable HTML pages.

> README files are an essential part of any analysis workflow, so that your future self or your collaborators are able to understand what they need to know. Git and Github encourage this practice for every repository. [Click here to learn more about README files associated with biomedical datasets/analyses](https://datamanagement.hms.harvard.edu/readme-files).

Let's turn our `README.md` file for this Git repository into something more meaningful by added some boilerplate text and helpful information to the small amount of text already there:

```
## Overview
Our code will demonstrate the different code snippets that have been used for programming
classes. We will have this written in both R and Python. 

## Installation
The full suite of code will require the Tmisc and dplyr R packages; 
matplotlib and seaborn for Python

## Usage
Simply fire up RStudio for trying out your R code, or Spyder for your Python code.

## Getting help

## Contributors
Contributions and references are included in the source code files.

## References
Contributions and references are included in the source code files.

## Licensing
This is all available as CC BY 4.0 license. Enjoy!
```

Save the changes to your file.

Let's also open ANOTHER file?  Copy & paste this code:

```
EXAMPLE CODE
```

Save this file as well, and go back to GitHub Desktop. WHAT DOES IT LOOK LIKE?

When you click on the filename, you will see that these new lines of text appear; this lets us know that Git is able to see changes in your file but at the moment these changes haven’t been recorded in an official ‘snapshot’ of your repository. To do this we need to **add** (**stage**) first and then **commit** these changes to record them in the 'snapshot', just as we did before.



> **Text Editors:**
>
> When creating a plain text document, you will want to use a text editor like Atom, TextWrangler/Sublime Text (Mac) or NotePad++ (Windows) instead of Microscoft Word or the default text editors. You will also want to make sure that you save it as plain text. There are a [large number of free and paid text editors available](https://en.wikipedia.org/wiki/List_of_text_editors) to choose from. In a pinch, you can always use TextEdit (Mac) or Notepad (Windows).

In the context of GitKraken when you **stage** your changes, it is similar to the **add** command on the command line interface. You can add several changes in the staging area, and only **commit** when you are ready. 

Since we wish to keep all the different types of changes as separate commits, we will stage and commit first the documentation change to the README file, and then the code change in the Rscript file. 

First, stage only the `README.md` file, and, as we did with our previous initial commit, include a change message, and click on the Commit button:

<img src="../img/2.new-pre_commit_readme_change.png" width="700" align="center">

Again, you'll see our timeline has changed to include this commit. Now, stage the changed R file and include a meaningful change message, and click Commit. Our timeline should now contain these two serial commits:

<img src="../img/2.new-post_serial_commit_changes.png" width="700" align="center">

There may be times, however, when we wish to ensure that we save a coordinated set of changes. For example, if we want to make coordinated changes to multiple files it makes sense to make the changes and then stage (add) and commit all the updated files all together (**atomic commit**). 

Let's say we want to update the code in the `scriplets.R` file to the following wherein we want to use the `util_functions.R` in the code. Remember that the `util_functions.R` is the Rscript file we left behind in the folder we had downloaded. 

1. Let's update the `scriplets.R` file with the following information and save it:

```R
#!/usr/bin/env Rscript

# This script will include a collection of small scripts steps
# often seen as example code. We're using this solely for demo purposes

# Put globals, installs, and sources here
source("./util_functions.R")

# Put functions here
#   1. Prints hello world
hello_world <- function() {
  myString <- "Hello, World!"
  print (myString)
}

# main code

hello_world()

square_it(10)

montecarloPi(3000)

# END
```

2. Now, let's move the `util_functions.R` script file from the downloaded `example_files` folder into the `code` folder in our new repo. 

When we return to GitKraken, it has noticed the two changes. Since the change in the main code file depends on the presence of this other file, we need to ensure this commit (snapshot) captures these inter-dependent changes. So, let's stage both files, give a meaningful commit message reflecting this process, and then commit! 

Your repo should now look like the following:

<img src="../img/2.new-post_coordinated_commit_change.png" width="700" align="center">

***

**Exercise #1**

1. Create a repository `learning_github` in GitKraken. Make sure to create it both locally, and remotely on github.com.
2. Find the folder on your local computer, and add a couple of small text files to it from your computer. 
3. Create a new plain text file called `data-file.txt`, add a line or 2 of content to it and save it to the `learning_github` folder.
4. Go to GitKraken, and commit the change with an approriate message.
5. Switch repos back to the `gitkraken_workshop` repo.

***

* Materials used in these lessons are derived from Daniel van Strien's ["An Introduction to Version Control Using GitHub Desktop,"](http://programminghistorian.org/lessons/getting-started-with-github-desktop), Programming Historian, (17 June 2016). [The Programming Historian ISSN 2397-2068](http://programminghistorian.org/), is released under the [Creative Commons Attribution license](https://creativecommons.org/licenses/by/4.0/) (CC BY 4.0).*

* Materials are also derived from [Software Carpentry instructional material](https://swcarpentry.github.io/git-novice/). These materials are also licensed under the [Creative Commons Attribution license](https://creativecommons.org/licenses/by/4.0/) (CC BY 4.0).*
