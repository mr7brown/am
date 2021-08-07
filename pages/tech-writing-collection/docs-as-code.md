---
title: Docs as Code
permalink: docs-as-code.html
layout: docs-as-code
---

Over the past few years technology has boomed and the general technical aptitude of companies has improved. With this increase in technical aptitude, the traditional ways of creating documentation are also shifting. In this post we will look two different approaches to documentation and documentation management: Content Management Systems (CMS) an docs as code.

## Old-School CMS

First, let's start with the good. Content Management Systems like SharePoint or Dropbox provide a place to store documents in a manner that nearly all professionals are familiar with. They are also great solutions for companies or teams with a small set of documentation, especially if the documents are template based.

However, this reality is rapidly fading. Everything has become digitial and with Covid-19 forcing many of us to work remotely, online authoring is already seeing rapid increases. For traditional Content Management Systems and workflows, online authoring is a glaring weakness. When document sets become large, they become difficult and tedious to maintain. Let's take a look at an actual example that I came across and solved at HBO.

### Case Study 1: Global Updates

At HBO we maintain a specification library of around 50 documents that provide content producers with a set of technical requirements that must be met before the content is ingested into the media pipeline. While each specification had variations, there were also some sections that were identical. 

And here is the problem with the CMS model. 

If a global update needs to be made to a section that is common across 50 specs, then all 50 specs have to be updated manually. This is tedious, error prone, and simply not effective.


## New-School Docs as Code

If we take the same case study and use a docs as code approach, the update only needs to be made once. With a modern approach that uses [Git + Github or GitLab](/https://git-scm.com/), a text editor (my favorite is [Visual Studio Code](https://code.visualstudio.com/)), and a plugin (Liquid) or component (React), you can do something like this:

1. Create an `_includes` folder.
2. Create a file that contains global text that will be used across multiple documents.
3. Embed the `includes` in each doc.

With the `includes` file embedded in each doc, global updates can be made by updating one file. 

## Collaboration

At some point in time most of us have felt the pain of collaborating in a Word doc (even the online version is dreadful). That's because Microsoft Word and CMS-based approaches were built in a time where that was the only option availble. That is no longer true, which is why many companies, tech or otherwise, are moving from the CMS model to online authoring solutions.

### Case Study 2: Three Writers, One Document

Collaboration in the Word/CMS world goes something like:

1. Recieve request for doc.
2. One person begins writing, and sends the working doc via email.
3. One at a time the doc is sent back and forth and changes are manually merged in.
4. Versions become confusing, which typically requires a collaboration meeting to fix the errors.
5. Doc is approved and published.

Compared to collaboration when docs are managed like code:

1. Recieve request for doc.
2. Roles are defined for the doc (one person will be responsible for merging files).
3. Each writer runs `git pull` and begins writing independent of each other.
4. Each writer commits and pushes changes where a differential (screenshot below) can be seen.
5. Files are merged and published.

<div class="post-image-container">
    <img class="post-image" src="images/diff.png" />
</div>

For the CMS approach there is a bottleneck for writing. Since there is one master document, it is easier to keep all the changes in that document. Otherwise you are bound to run into formatting issues, as well as human error. For the docs as code approach there is no bottleneck. Each writer can write independently and have each change merged in at the end. And as an added bonus, there is a permanent log of updates made, which can be reverted at any time. So long versioning.

## Closing Thoughts

This post is designed as an introduction to docs as code. In the next post [Technical Writing Essentials](/tw-essentials), we will look at job descriptions from some top companies, which strengthen the case for docs as code. Additionally, the post will cover some of the requisite skills and resume builders for a career as a Technical Writer.
