---
layout: default
title: "Working with branches"
author: "Heather Wick"
---

## Learning objectives
* Learn what a branch is and what they are useful for
* Learn how to create a branch and switch between branches in GitHub Desktop
* Learn how to make changes to branches in GitHub Desktop
* Learn how to merge branches in GitHub Desktop
* Explore branch management on GitHub.com

## What is a branch?

So far we've demonstrated how Git captures a history of your repository in a series of snapshots, made every time you commit a new change to your repository. But what if we want to make some more experimental changes to our repository? Perhaps there is a bug that needs to be fixed, or a new feature we want to add to a pipeline, but we're not quite sure if these changes will work or mesh properly with our main code. Or, maybe we have a collaborator that wants to make contribuitons, but we want to make sure that we preserve our original repository as-is as a backup before reviewing and incorporating their contributions. For these types of experimental fixes or changes, we can create a new **branch** independent from `main` to make changes to while keeping our `main` safe from any unstable code. This new **branch** will have its own history of commits separate from `main`.

The illustration below shows a repository where each commit is represented by a circle and the edges show their linear relationship. Someone has made a new branch, `Some Feature`, independent from `main`. `Some Feature` has some of its own commits, but its history , with its own history of commits:

<p align="center">
  <img src="../img/9.GHD_new_branch.png" width="800">
  <em>image source: https://www.atlassian.com/git/tutorials/using-branches/git-merge</em>
</p>

Once you are done perfecting the changes made to the new branch, if you decide you want to keep and incorporate your changes into your `main` repository, you can **merge** the new branch back into `main`. This creates a single, unified repository again:

<p align="center">
  <img src="../img/9.GHD_merge_branch.png" width="800">
  <em>image source: https://www.atlassian.com/git/tutorials/using-branches/git-merge</em>
</p>

Or, if your experimenting didn't work, you can keep it separate and continue working on it or ignore it altogether, without jeopardizing `main`.

## How to create a branch in GitHub Desktop

To create a new branch in GitHub Desktop, click the arrow next to `Current Branch` in the middle tab of your repository bar. From the drop down menu's `Branches` tab, you'll see a button that says `New Branch`:

<p align="center">
  <img src="../img/9.GHD_make_branch_1.png" width="800">
</p>

Click `New Branch`, and you'll get a popup asking you to name the branch. There is also a reminder that your new branch will be based off of `main`, meaning that it will contain the same history of commits as `main` up until the point that the two branches diverged. If you had multiple branches, GitHub Desktop would let you choose which branch you would like to base the new branch from. Give your new branch an appropriate name (we chose `test_branch`), then click `Create Branch`:

<p align="center">
  <img src="../img/9.GHD_make_branch_1.png" width="800">
</p>

You'll notice that the middle tab of your repository bar now indicates that your Current Branch is now `test_branch`.

## Switching between branches

Earlier, we mentioned that branch histories are independent. That means that you can continue making changes to `main` even though you are working in a new branch. You can switch back and forth between branches easily. Simply click the arrow next to `Current Branch` in the middle tab of your repository bar. Now your drop down menu will display all available branches for your current repository in the `Branches` tab. The branch you're currently in will have a check mark next to the name. Simply select whichever branch you would like to navigate to:

<p align="center">
  <img src="../img/9.GHD_switch_branch.png" width="800">
</p>

For now though, let's stay in `test_branch`

> **What if I decide I want to delete a branch?**
> Maybe you have abandoned your experimental code and want to clean up the clutter. To delete a branch, make sure your `Current Branch` is set to the branch you would like to delete. Then, select `Branch` from the menu bar, and select `Delete Branch` from the drop down menu. GitHub Desktop will produce a pop up to confirm before you delete your branch, but be careful: Deleting a branch is permanent!

## Making changes (commits) to your new branch

Making a change to a branch is just like making a change to `main`. Let's give it a try. Navigate to the `Changes` tab on the left and then click the button to `Open the repository in your external editor`. Go to your readme and add this line under the first header and save the readme file:

```
This line of code was introduced in the lesson on branches!
```

<p align="center">
  <img src="../img/9.GHD_change_readme.png" width="800">
</p>

Just as before, you'll immediately see the change in the `Changes` tab. Go ahead and commit this change by clicking `Commit to test_branch`:

<p align="center">
  <img src="../img/9.GHD_commit_branch.png" width="800">
</p>

And that's all there is to it! If you were to set your `Current Branch` to `main` and open your readme file in your external text editor, that line of text we added would not be there, because the change we made is unique to `test_branch`. Go ahead and see for yourself!

### Publishing your branch to GitHub

One last step: let's publish our new branch to GitHub.com. From the main `Changes` tab, click the **`Publish branch`** button to publish it to Remote:

<p align="center">
  <img src="../img/9.GHD_publish_branch.png" width="800">
</p>

If you go to your repo on GitHub.com, you'll see that the branch has been published:

<p align="center">
  <img src="../img/9.GHD_branch_on_GitHub.png" width="800">
</p>

## Merging branches

Once you're done making changes to your new branch, and you've decided you want to keep these changes and incorporate them into your `main` repo, you will want to **merge** branches back together. This will keep your repository organized so you don't end up with lots of different branches with lots of different versions. To do this, we'll be making a **pull** request from `main`. But before we do that, there's something important to consider:

### What if I don't to keep all the changes I made?

Sometimes, you might find that there are some changes you want to incorporate from your new branch, but other changes you want to leave behind. This is called **Cherry-Picking**. When we were exploring options for commits in the previous lesson, this was one of the options we saw in the drop down menu for commits in the `History` tab. **We're going to keep all of our changes, but for demonstration purposes let's show you how to cherry-pick in case you want to in the future:**

While still in `test_branch`, if you go to your `History` tab and right click the most recent commit we made, you'll see **`Cherry-pick Commit...`** in the drop down menu:

<p align="center">
  <img src="../img/9.GHD_cherry_pick_1.png" width="800">
</p>

If you select this, it will give you the option to **cherry-pick** the commit to a branch:

<p align="center">
  <img src="../img/9.GHD_cherry_pick_2.png" width="800">
</p>

**For now though, we're going to skip this -- just close the pop-up without cherry-picking.**

### Making a pull request to merge branches

Instead, we're going to keep all (one) of our changes and merge `test_branch` with `main` via a **pull request**. You'll notice a new highlighted box with a blue button that gives the option to **`Preview Pull Request`** (you may notice that this button has a drop down menu to skip straight to `Create Pull Request`, but we recommend reviewing your pull request first):

<p align="center">
  <img src="../img/9.GHD_pull_request_1.png" width="800">
</p>

If you click this button, it will pull up a summary of changes, with the option to **`Create Pull Request`**:

<p align="center">
  <img src="../img/9.GHD_preview_pull_request.png" width="800">
</p>

Clicking this will immediately open your repo on GitHub.com. Similar to when making a commit, you'll be prompted for a title and a description for your pull request. Go ahead and add a brief description and click the green **`Create pull request`** button

<p align="center">
  <img src="../img/9.GHD_create_pull_request_github.png" width="800">
</p>

> Note: you'll see a message up top here that says "Able to merge. These branches can be automatically merged." There may be cases where your branches conflict, just as commits can conflict, and they'll need to be manually reviewed.

After a moment of processing, the page will show you a number of useful options, including the ability to **require review from specific users** (useful if you have multiple people working on a project that belongs primarily to one person who is the main editor) or to turn on debugging options through **continuous integration**. Notice we have a nice green checkmark indicating that **This branch has no conflicts wiht the base branch** meaning we can merge these branches automatically without having to review manually. 

<p align="center">
  <img src="../img/9.GHD_merge_pull_request_github.png" width="800">
</p>

Under that is a big green button that says **`Merge pull request`**. If you click the arrow on the button, there are several options:

**1) Create a merge commit** -- This will add all commits we made to the `test_branch` into `main`. This is useful for seeing individual changes that were made and even changing them down the road. If changes were also made in `main`, the commits will be interleaved.

**2) Squash and merge** -- This will condense, or "squash", all the commits from `test_branch` into a single commit. This is useful if you know you won't want to make any changes to individual commits after merging, or don't need the complete history from the `test_branch`

**2) Rebase and merge** -- This will add all commits from `test_branch` to the end of `main` but not create an extra commit -- this makes a somewhat cleaner history but does not indicate a merge commit

<p align="center">
  <img src="../img/9.GHD_merge_options_github.png" width="400">
</p>

####THIS DOES NOT APPEAR TO ACTUALY WORK -- THE BUTTONS ARE ALL THERE BUT GREYED OUT
**Before we go ahead and merge on GitHub.com, let's go see what this all looks like in GitHub Desktop**.
If you click the `Current branch` tab from the repository bar and go to the `Pull requests` tab, you'll see the pull request as well as a button to **`Choose a branch to merge into test_branch`**

<p align="center">
  <img src="../img/9.GHD_merge_pull_request_GHD_1.png" width="800">
</p>

If you click this button, you'll see a pop up that resembles the options we saw on GitHub.com:

<p align="center">
  <img src="../img/9.GHD_merge_pull_request_GHD_2.png" width="800">
</p>

We also have the same 3 options for merging as well:

<p align="center">
  <img src="../img/9.GHD_merge_pull_request_GHD_3.png" width="400">
</p>
####END WEIRD SECTION THAT DOESN"T ACTUALLY WORK

Go ahead and merge your branches using the default setting, clicking the green `Merge Pull Request` button.
Then, you'll be prompted to **`Confirm merge`**:

<p align="center">
  <img src="../img/9.GHD_merge_pull_request_github_confirm.png" width="800">
</p>

You'll now see that the pull request has been completed on GitHub.Com

<p align="center">
  <img src="../img/9.GHD_merge_pull_request_github_done.png" width="800">
</p>

Now we still have to sync our remote origin with our local repo. You'll see you now have a pull request:

<p align="center">
9.GHD_pull_origin_merge
</p>

Go ahead and click `Pull origin` and then navigate to your `History` tab, and you'll see the comit from `test_branch` which updated the readme file as well as the commit which merged the two branches:

<p align="center">
9.GHD_pull_origin_merge_history.
</p>

## How to create a branch on GitHub.com

We've already been through how to create a pull request and merge branches on GitHub.com because making a pull request on GitHub Desktop requires GitHub, but it may be useful for you to know how to create a branch on GitHub.com as well.

From your repository on GitHub.com, click on the `main` button in the upper left and you'll see an text box with the prompt to "Find or create a branch." Give your branch an appropriate name (we chose `remote_test_branch`), then click **`Create`** directly below:

9.GHD_create_branch_github_2

Once you've created your branch, you can even see the new branch on GitHub Desktop:

9.GHD_create_branch_github_3

*** 

Exercise: Add this line to your readme file on GitHub.com, then observe any changes to your local repo in GitHub Desktop.

```
 This line was introduced on my remote branch!
```
9.GHD_create_branch_github_4

***

You'll see these changes are automatically pushed to the your local `remote_test_branch` and is visble on GitHub.com

9.GHD_create_branch_github_5

## Merging directly from GitHub.com

If you click on the **`Pull request`** button in the upper left, you'll be brought to a new screen and see an option to **`Compare and pull request`** pushes that GitHub.com has noticed in your new test branch:

9.GHD_create_branch_github_pull

Clicking this button will bring you to a similar screen we saw before when initiating a pull from GitHub Dekstop. Go ahead and create the pull request, then confirm the pull request, just as before. Once you have confirmation that it's been synced. You'll see that GitHub Desktop will already have the merge incorporated to main.


