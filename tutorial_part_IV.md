# Part IV: Contributing to Projects

## Key Topics
1. Contributing to projects.
2. Further reading and resources for help.

## Defining public versus private projects
For the sake of this tutorial, we categorize projects into two:
1. __*Private:*__ When you have access to push to the *master*/*main* branch of the remote repository. For instance, on Github, when you create repository, you will get this access. Similarly, if someone else creates a repository and adds you as a [*collaborator*](https://www.geeksforgeeks.org/what-are-github-collaborators/), you will get this access. 

    In this case, in general, you can directly push your changes as you have been doing in this tutorial.

2. __*Public:*__ As you can imagine, someone who has access to push to a repository has a lot of power. They could change some parts of your code which could potentially cause it to break, etc. Even though you could track the commit history and revert to older commits, etc., it easy to imagine how inconvenient this would be. 

    So, in many cases, projects that are visible to all are protected; i.e., you cannot push to them without approval from someone in charge. And even if you could, it is just better not to. 

    Even in this case, you can and should contribute. Here, we explore how. 

## Contributing to open source projects
### What are open source projects
The term [*open source*](https://opensource.com/article/18/2/coining-term-open-source-software) was coined by Christine Peterson in 1998 in the context of software. According to [opensource.com](https://opensource.com/resources/what-open-source), 
>Open source software is software with source code that anyone can inspect, modify, and enhance.

Basically, these are software where you can see the *source code*; i.e., the code that the computer is running when executing the software. 

Users of Python might be familiar with libraries such as numpy, scipy, scikit-learn, PyTorch, TensorFlow, among many others. These are some of the many excellent open source projects out there.

### Why you should contribute
Contributing to open source projects is an excellent way to build skills in writing software and learning its best practises. It can also be a great way to learn from other talented programmers and improve skills. 

## How to merge your changes into the master project
Let's say that your ideas for new apps were indeed something valuable and you wanted to contribute to this project. 

Go ahead and try to push your repo (`msater` branch) to the `public` branch of this project using:
```
git push origin master:public 
```

You will see that the push is unsuccessful and aborted. This is because this branch is protected just as it would be for many open source projects. 

The way to propose these changes is by opening a "pull request". 
1. Visit https://github.com/architdatar/quick-git-tutorial/tree/public. 
2. Click the **Pull request** button on the top left and follow instructions [here](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request-from-a-fork) to create a pull request to merge your `main` branch into the `public` branch of this project. 

If you had been wondering why we started out by *forking* the repo earlier on, this is why: to allow you to create a pull request.  

Congratulations! You now know how and why to contribute to open source projects. 

## Resources and next steps
This tutorial was written to help you get your toes wet in the world of Git and version control. As mentioned earlier, this is nowhere close to being exhaustive. The best way to learn is by doing. 

Here are the resources that we have referred to in this tutorial thus far. 

1. Chacon, S. and Straub, B. [Pro git](https://git-scm.com/book/en/v2), 2014.
2. Atlassian tutorials (https://www.atlassian.com/git).
3. Git documentation using `man git` or `man git-<COMMAND>` in the terminal. 
4. [Git cheatsheet](file:///Users/architdatar_1/Downloads/SWTM-2088_Atlassian-Git-Cheatsheet.pdf) by Atlassian.
