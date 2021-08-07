---
title: Git Overview
permalink: git.html
layout: git-collection
---

In this post we will look at Git, the top version control tool used by tech companies. While many of you may be familiar with using Git or have at least heard of it, the purpose of the Git collection is to provide you with the information and skills required from a tech writing standpoint. Most guides are created with the devloper in mind and contain more information than tech writers will ever use. 

From a chronological standpoint, this post includes:

1. An overview of Git and how technical writers use it.
1. Introduction to the four Git environments.
1. Prep for part 2/3 of the Git Collection.

## Git Overview

Git is a version control tool that interacts with a remote repository and your computer's local file system, and while it is not the only version control tool, it is, by far, the most popular tool used by tech companies today.

From a technical writing standpoint, Git is used similar to the ways developers or engineers use it. The main difference is that the workflow is simplified (since most of the advanced functions are not needed). This simplification allows technical writers to focus on the primary functions:

1. Collaborative workflow.
1. Version control.
1. Efficiency.

Below is an example of the Git environment, as well as an example of a common technical writing workflow with Git and a docs as code approach.

<div class="post-image-container">
    <img class="post-image" src="images/git-flow.png" />
</div>

While this may or may not seem simplistic, there is a method to this. In my experience, technical writers begin to understand the commands for Git, but they only seem to understand the four environments when everything is working as intented - AKA `git pull`, `git add`, `git commit`, `git push`. When something breaks (and something will), they have a difficult time understanding where in the chain something broke.

I think having a strong conceptual model makes problem solving, working in teams with multiple writers, and becoming a power user easier.

<hr>

### Working Directory

The first enviromment, or the `working directory`, can be defined as the computer's local file system. Git interacts with a computer's local file system by keeping an index of the contents of a folder - better known as a repository.  

The screenshot below is of my local file system and the repository used for my website.

<div class="post-image-container">
    <img class="post-image" src="images/local.png" />
</div>

For Git to work, you must initiate it within a folder by running:

```
$ git init
```

Once you initialize a repository, Git takes a snapshot of the folder and begins monitoring it by a process called indexing.

{% include important.html content="Don't worry about the commands for now. The commands in this post are for illustration only." %}

### Index

To understand indexing, you should think of it as Git comparing two seperate points: `HEAD` and `working directory`. 

Let's think of practical example using a file cabinet. After first initializing a repository, Git takes a snapshot of the file cabinet (`working directory`) at that present time.

This snapshot becomes known as the `HEAD`. In other words, the `HEAD` is set to the last commit.

Sticking with the file cabinet example, say that in our initial commit (`git init`) we had 10 files, and then we create a new file. Through indexing, Git compares the `HEAD` (10 files) to the currrent `working directory` (11 files) and notices that there is a difference. This difference is better known as a differential (similar to the screenshot of the terminal below).

<div class="post-image-container">
    <img class="post-image" src="images/git-add.png" />
</div>


Put simply, Git is actively comparing the last commit to the `working directory` for differences. 


### Head

As discussed, the `HEAD` is effectively a snapshot of the last commited change. But, unlike a Word document that only tracks the current state, Git indexs each commit. Meaning, each time you run 

``` 
$ git commit -m "<enter commit message>"
```

you create a new record, which can be referenced or reverted at any time (more on this in future posts).

An important note here is that `HEAD` is where people tend to get into trouble. That is because the state is completely different than the `working directory` and `index`. Unlike the previous environments, updates can still be reverted, but it can be a tricky process.

### Remote Repository

While having an index of files, folders, etc. on your personal computer is great and a step up from having an unmanaged file system, you can take your local directory further by creating a `remote repository`. As you may expect, a `remote repository` is essentially a web-based storage location for your files. However, remote repositories like Github allow you to not only store files, remote repos can also become a platform for hosting a website (Git, Github, and Github pages are what I use for workflow on this site).

## Closing Thoughts

By now, you should have a solid understanding of how Git is used. In the next post, [Getting Started w/ Git](/git-getting-started), we will create a remote repository and begin using it just like developers do. We will also begin creating branches, go over some common interview questions, and discuss some essentials for managing workflow.



