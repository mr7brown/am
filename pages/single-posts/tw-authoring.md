---
title: Information Architecture & Documentation Management
permalink: tw-architecture.html
layout: docs-as-code
---

The purpose of this post is to highlight why documentation management is important and how we can achieve effective documentation by creating logical information architecture.

Unlike other documentation where the goal is to get readers to stay on the page for as long as possible, technical docmentation follows a different flow. For example, how many times have you clicked on a headline to read a specific portion of the article, only to find a tiny blurb near the end of the article?

If you're like me, this happens often and it's pretty annoying. It's especially annoying in technical or informative reading materials, and that's why technical writers often use an inverted writing style.

## Inverted Pyramid

An inverted writing style or inverted pyramid approach essentially means that the most important information comes first and becomes more general as the material progresses.

<div class="post-image-container">
    <img class="post-image"  src="images/pyramid.jpeg" />
</div>

The reason this is essential for information architecture is because it aligns with how we interact with information. This is because most people do not read documentation in its entirety. They skim instead. 

Another thing to note is that people reading technical documentation are usually looking for a specific piece of information, and not drawn out prose. 

Make it easy for them to find what they need.

## Information Architecture

Now that we established the inverted pyramid as the foundation we can begin building the other aspects of technical documentation. The next step and the glue to the different methods for documentation management is information architecture. 

One way to think of this term is to think of a web of information, and within each web you need to solve:

1. What is the most important information?
1. How will users interact with the content?
1. What is the best medium to house and display the content?

Once you answer some of the foundational questions, you can then begin figuring out how the pieces fit together. For example, if you have collections of loosely related material, you may need a knowledge base. If you have a documentation set that is more of a program, then you may need to host a documentation portal (static or otherwise). Or, maybe you have a library of unrelated documents that can be effectively managed with a simple Content Management System (CMS) like SharePoint. Let's look at all three.

## Knowledge Base

As previously mentioned, a knowledge base can be a useful way to provide team information in a single location. Too often you see organizations with information all over the place, and this lack of cohesion and sound information architecture places strain on the people looking for documentation.

During my time working at Facebook I was taked with solving this exact issue. The team I worked with had six or seven different repositories and processes for finding information and never really knew where or how to find the information that they needed.

Below is an example of a simple layout I implemented to collate six repositories and processes for information gathering into a single source of truth.

<div class="post-image-container">
    <img class="post-image"  src="images/fb-wiki.png" />
</div>



{% include important.html content="You don't have to be fancy. Sometimes simple is better." %}

## Documentation Portals (Static Sites)

A second scenario that you may come across regarding documentation management is the need for a public or internal facing site comprised of information designed to be built in a tiered manner.

To illutrate this, let's look at an example from HBO. Third party partners can't simply deliver content to HBO - because they need more information than where/how to upload files. IF that is all that was required, there would be no need for a Media Supply Chain team. 

And this is where information architecture comes into play. Knowing that there are more steps to the process, technical writers and documentation engineers become tasked with understanding the process for delivery and reproducing that knoweldge for unfamiliar parties. Once that is done, you can begin laying out the information that moves progressively:

1. Onboarding.
1. Technical assessments.
1. Sample delivery packages.
1. Delivery requirements.
1. Delivery.

Similar to the image below.

<div class="post-image-container">
    <img class="post-image" src="images/wm-image.png" />
</div>

In my opinion static sites are the way to go when creating documentation portals. They are easy to set up (if you know what you are doing), they don't require a CMS (you can host securely on GitLab), and they are basically costless.

I plan to dedicate an entire post on static site generators and why Google, Facebook, Amazon, HBO, Netflix and the like are all using them.

## CMS

The last topic for this post and the simplest to understand is the Content Management System. Most times they are treated as a dumping ground for documents of all types. While they may not be as robust or as fancy as static sites or knowledge bases, you should still try to create a smart information architecture! Use librariers, folders, etc.

## Closing Thoughts

Hopefully this post provided you with some new ways of thinking about presenting information and how to create an information archtecture that best serves your readers.
