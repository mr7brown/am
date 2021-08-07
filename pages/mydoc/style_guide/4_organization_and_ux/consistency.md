---
title: Consistency
keywords: "Style Guide, Grammar, Technical Writing, Technical Editing"
layout: style-ux
permalink: consistency.html
folder: mydoc
---

## Technical Writing at a glance

Unlike other forms of writing, technical writing is better with less variation. For example, when describing the terminal, you should refer to it the same way throughout a document and throughout the whole library of information. 

With technical information, it is easy to cause confusion just by referring to a program, application, or process in a different way. Being consistent helps reduce the mental load that's put on users. For more on cognitive load, see [8 ways to reduce cognitive load: Part 1](https://uxplanet.org/8-ways-to-reduce-cognitive-load-part-1-cc2048d1b157).

## Examples

<i class="fa fa-thumbs-down fa-lg" style="color: red;"></i> **Not recommended:** The filename should match the title record. If the file name does not match, the submission will be rejected. <br><br>
<i class="fa fa-thumbs-up fa-lg" style="color: green;"></i> **Recommended:** The filename should match the title record. If the filename does not match, the submission will be rejected.

In the example above, filename is spelled differently in the two examples. For more on spelling, refer to the [Spelling](/spelling) section of this style guide.
<br><br>

<i class="fa fa-thumbs-down fa-lg" style="color: red;"></i> **Not recommended:** Run `git log --oneline` from your terminal...copy the commit that you want to revert, then type 'q' in the shell to exit.<br><br>
<i class="fa fa-thumbs-up fa-lg" style="color: green;"></i> **Recommended:** Run `git log --oneline` from your terminal...copy the commit that you want to revert, then type 'q' to exit.

In the example above, introducing the user to both terminal and shell in the same set of instructions can trip up a novice user. It's best to avoid introducing new terms in the middle of instructions. Staying consistent and using one term is good, but rewriting the sentence to remove a need for two instances of the same word is better.

## More on consistency

In addition to consistent terminology, formatting should also be consistent. In general, try to avoid:

* Having inconsistent font/heading sizes.
* Increasing or decreasing the amount of white space between sections unless there is a good reason.
