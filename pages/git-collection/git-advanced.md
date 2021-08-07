---
title: Git Advanced Commands
permalink: git-advanced.html
layout: git-collection
---

At this point in the Git Collection you should understand what it is, how it is used, and have begun using it. This post takes all the lessons learned so far and takes them a step further by looking at branching (which is typical for projects with multiple contributors).

By the end of the collection, you should know and be able to demonstrate ~80-90% of how technical writers work with Git. The only reason it is not 100% of the knowledge is because there will be some nuances that are different between each company. For example, at Google the Google Assistant team is fairly large and required deeper control over the code base. So instead of using Git and Github, the team developed Cider and Piper, which were essentially clones of Git and Github. As for HBO, instead of Github they use GitLab, which requires an SSH connection - so `git push` is a bit different.

It is difficult to account for the nuances and in the end, part of being a technical writer is understanding the 80% and researching the rest.

## Branching

When working on a team with multiple contributors a best practice is to work with branches. By default, there is a `master` branch that is used for the `HEAD`. The image below is a pretty good depiction of branching in Git.

<div class="post-image-container">
    <img class="post-image" src="images/git-merge.png" />
</div>

Essentially, branching allows you to work independently, while not impacting the main source of the information or code. First, let's look at an example of how this works at HBO (and most companies), then we will go through an exercise.

### Branching Example

At HBO, I am responsible for all content updates to our Partner Hub (a site where 3rd-party partners can see our delivery requirements), and I am also responsible for front-end development/maintenance of the Partner Hub. However, there is also an Application Architecture team that is responsible for deployments, security, compliance, etc., and two other full-stack developers that also contribute to the code base.

At any given time, we are all working on something that impacts the code and the prod. site. For this reason, and many others, we cannot work on the `master` branch.

Instead, we create branches so that we can all work independently of each other. And once we are finished updating, we push our changes to GitLab and create a merge request. A merge request basically means that an update was made in a new branch, call it **branch-a**, and those updates are ready to be reviewed and then merged into the `master` branch.

The result is a workflow similar to the image below.


<div class="post-image-container">
    <img class="post-image" src="images/deployment.png" />
</div>


### Creating a Branch

Let's start creating branches!

{% include important.html content="A good way to gain experience is to create branches and merge them into your personal Github account." %}

We will start with the project created in [Getting Started with Git](/git-getting-started.html#git-exercise). Alternatively, if you have an existing Git repo, feel free to create your branches there - but skip to **Step 3**.

1. Open a new terminal window and navigate to the `<new-git-repo>` folder:
```
$ cd desktop/new-git-repo
```
1. A good practice when starting a new terminal session in a folder is to check the status:
```
# Checking the status tells you if files need to be commited, tracked, etc.
$ git status
```
* Prior to creating a new branch you should make sure that you have a clean working directory to avoid merge conflicts or lost work.
1. Check to see which branch you are on:
```
# The asterisk '*' shows you the branch you are currently on
$ git branch
```
* Since you have not created additional branches, you should only see `*master`
1. Create a new branch:
```
# Portfolio is only place holder, you can enter any name for the branch
$ git branch portfolio
```
1. Switch from the `master` branch to the `portfolio` branch:
```
$ git checkout portfolio
```
* A shortcut for creating a branch `git branch <branch name>` and switching to the branch `git checkout <branch name>` is to write `git checkout -b <branch name>`. This creates a new branch and switches to the branch in one command.
1. Check to see that you are on the `portfolio` branch:
```
# The asterisk should be next to 'portfolio'
$ git branch
```

## Edit, Push, Merge, and Pull New Branch

Now that you have created a new branch and your terminal is pointed to the branch, you can create files, edit files, etc. 

Before moving on to the rest of this section, try refering back to how to create, add, and commit updates to the repository. Don't worry if you don't remember or if you need to refer to the previous post. The steps are below as well.

### Edit

1. Check to see which branch you are on:
```
$ git branch
```
* Even though this was the last command entered, I am making this step one to establish a habit - if/when you work on complex projects with multiple branches, it is easy to forget which branch you are on and update the wrong branch.
1. Create a new file `portfolio.md`:
```
$ touch portfolio.md
```
* You can also create a file and add text to it, for more on this, check out my [Linux/OSX Collection](/tech-blog.html#linux-collection-coming-soon) for more.
1. Check to see the update:
```
$ git status
```
1. Tell Git to track the file and add it to the `index`:
```
$ git add portfolio.md
```
1. Commit changes:
```
$ git commit -m "<enter descriptive mesage>"
```

### Push

1. Push commit:
```
$ git push --set-upstream origin portfolio
```
* When adding a new branch to Github, you need to enter `--set-upstream origin <branch name>` to `git push`. Subsequent pushes do not require `--set upstream origin`, only `git push`. 

### Merge

Before the updates can be seen on Github, you need to merge the changes from the `portfolio` branch to the `master` branch on Github.

To begin, Go to the Github repo for the `<new-git-repo>`. You should see a **Compare & pull request** button near the top of the page:

<div class="post-image-container">
    <img class="post-image" src="images/github-merge.png" />
</div>

1. Click the **Compare and pull request** button.
1. Enter a descriptive title for the commit, as well as a detailed description of what is in the commit - then click the **Create pull request** button.
1. Click the **Merge pull request** button, followed by the **Confirm merge request** button.
* You won't have merge conflicts since you are not merging multiple branches.

You should now see a success message, which means that your branch has successfully been merged to the master branch on Github. Last step is to `pull` the `master` on Github into the `master` on your local directory.

### Pull

To ensure that your local `master` branch is in sync with the remote Github branch, you need to create a pull request. This request essentially takes the master branch from Github and compares it to your local `master` branch. If there are updates on the remote branch, the `pull` request makes the same updates to your local `master` branch.

1. From the `<new-git-repo>`, check the status and branch:
```
$ git status
$ git branch
```
* You should have a clean directory and be on the `portfolio` branch.
1. Switch to the master directory:
```
$ git checkout master
```
1. Pull the remote Github `master` branch into your local `working directory`:
```
$ git pull
```
1. Check the status:
```
$ git status
```

You should now have a local file system for the `<new-git-repo>` that matches what is on Github.

## Closing Thoughts

That's it! You have just worked through the typical lifecycle of a docs as code project. Minus working on actual files.

The last post of the collection [Mastering Git](/git-master.html) is short, but packs some handy shortcuts and best practices.
