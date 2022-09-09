# Quick Git Tutorial

<!-- ## Table of Contents -->

<!-- Add TOC -->

## Introduction
This tutorial is meant to be a quick start for someone  new to the world of version control. It is not meant to be exhaustive or deep by any stretch of the imagination, but is meant to be a compilation of the common uses of Git and most Googled references to address these problems. 

## Tutorial
This tutorial will walk you through a sample project in which you will provide feature ideas and pseudocode for apps you want to see built.  

- [__Part I__](tutorial_part_I.md) covers the basic steps which will enable you to pull code from your remote repository (hosted on Github.com), make changes to it and push those changes back to this remote repository.  
- [__Part II__](tutorial_part_II.md) covers slightly more advanced concepts such as handling branches, contributing to open source projects and next steps in your Git journey. 


## Command line interface (CLI) and why this tutorial uses it
There is a variety of graphical user interface (GUI) softwares available through which we can use Git such as Github Desktop and VS code. These make it quite easy to perform the most common applications with Git. However, in this tutorial, we insist on using the command line interface (CLI) tools. This is for the following reasons:
1. *Exhaustiveness:* To quote the [Pro Git](https://git-scm.com/book/en/v2) book, 
> ...the command line is the only place you can run all Git commands — most of the GUIs implement only a partial subset of Git functionality for simplicity. 
2. *Simplicity:* Due to this, it is much easier to use your favorite GUI when you learn the CLI than going the other way around.
3. *Universality:* There will be situations where the GUI will not be available. Most importantly, if you were to use it on a server which commonly occurs during deployment. 

Thus, we recommend that the users accept the short-term pain of using CLI to ease their long-term journey of version control.



## What is version control and why should you care?

> Version control is a system that records changes to a file or
set of files over time so that you can recall specific versions later.
>> -Pro Git

- Simply put, if you make a change to your code, Git allows you a way to go back to it. 

- Additionally, if you are developing something collaboratively, it allows you to incorporate code from your teammates. This can include new features, performance improvements, documentation, and a lot more. 

So, if you are developing any kind of an application in a modern setting, version control is a very powerful tool to have. 

## Git 

Git is the most widely used version control system. It was made by the same people who developed Linux (another great thing) and especially by Linus Torvalds. More history in given in [Pro Git](https://git-scm.com/book/en/v2). 



## References
1. Chacon, S. and Straub, B. [Pro git](https://git-scm.com/book/en/v2), 2014.
2. Burgess, A. [Easy version control with Git](https://code.tutsplus.com/tutorials/easy-version-control-with-git--net-7449), 2009. 
3. [A visual Git reference](https://marklodato.github.io/visual-git-guide/index-en.html)
4. Working directory definition https://stackoverflow.com/questions/36201342/git-where-exactly-is-the-working-directory. 
5. Staging: Crunchify https://crunchify.com/git-repository-what-stage-means-in-git-source-control/.
6. Staging: GeeksforGeeks https://www.geeksforgeeks.org/staging-in-git/. 
