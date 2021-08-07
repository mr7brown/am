---
title: Mastering Git
permalink: git-master.html
layout: git-collection
---

There has been a lot of information in this collection, but I wanted to be sure to provide a one-stop resource for Git. The final post in the collection is not as lengthy. However, it does contain some useful shortcuts and best practices that I've uncovered over the years.

## Git Shortcuts

I'm not going to try to provide a large list of Git shortcuts, since there are a million out there. But here are some of the quick hits that I use daily:

* `git add .` - Adds all files in the working directory. Only use this command if you know exactly what you are adding.
  * If you are unsure what you are adding, run `git status`.
* `git commit -am "<enter commit message"` - If you already have files previously tracked and commited, running this command combines the `git add` and `git commit` commands.
* `git checkout -b <enter-branch-name>` - This command combines the `git branch "<enter-branch-name>` and `git checkout <enter-branch-name>` commands. 

## Best Practices

The last section of the collection is best practices. This list is subjective and certainly not exhaustive, but again, this is what I have discovered and find to work well:

### General

1. Frequently check the status and branch. As projects become complex it is easy to update the wrong branch or be working on a branch that isn't current.
1. When working on projects with multiple contributors, it is a good practice to run `git pull` on the `master` branch before creating a new branch and making updates. This helps eliminate merge conflicts.
1. Write good commit messages. You will be surprised how frequently you need to reference a specific commit. Entering a good commit message helps you quickly identify exactly what changed - and the developer merging your changes will be grateful as well!

### Branching

1. When working with branches, it is importantant to delete your branches, but not until they have been fully merged to the `master` branch. By design, branches are not always up to date with the `master` branch. So, to avoid future merge conflicts be sure to delete your merged branches.
* Delete both the remote (Github) branch and the local branch `git branch -d <branch-name>`. Note: You can't delete a branch you are currently on. 
1. Categorize your branches. If you have code-based updates and text-based updates, seperate them into multiple branches. This makes it easier to review and you will likely run into situations where one commit is approved and one is rejected due to an error. Having two commits allows you to at least get one commit approved and merged.
  * One exception is if the text-based updates require the code-based updates to render properly. If this occurs, be sure to communicate this with the developer responsible for merging updates.

## Closing Thoughts

Thanks for reading through the Git collection! Hopefully it helped answer some questions surrounding Git and gave you with the foundational skills to help you practice Git, build/host a Git profile, and understand how Git is actually used in the tech writing world.

Be sure to check back soon for new collections and individual posts.