# Quick Git Tutorial

---


## Introduction
This tutorial is meant to be a quick start for someone  new to the world of version control. It is not meant to be exhaustive or deep by any stretch of the imagination, but is meant to be a compilation of the common uses of Git and most Googled references to address these problems. 

## What is version control and why should you care?

> Version control is a system that records changes to a file or
set of files over time so that you can recall specific versions later.
>> -Pro Git

Simply put, if you make a change to your code, Git allows you a way to go back to it. 

Additionally, if you are developing something collaboratively, it allows you to incorporate code from your teammates. This can include new features, performance improvements, documentation, and a lot more. 

So, if you are developing any kind of an application in a modern setting, version control is a very powerful tool to have. 

### Git 

Git is the most widely used version control system. It was made by the same people who developed Linux (another great thing) and especially by Linus Torvalds. More history in given in Pro Git. 


## How to get git

First, check if you have Git. If you don't download Git. 

### Windows
Open command prompt and type:
```
git --version
```
If you get a version, you have Git installed. Else, download it from using:
```
winget install --id Git.Git -e --source winget
```

### Mac
Open the terminal and type:
```
git --version
```
If you get a version, you have Git installed. Else, follow the prompts to download it. 

### Linux
Open the terminal and type:
```
git --version
```
If you get a version, you have Git installed. Else, if you are using Ubuntu or Debian-based distribution, type:
```
sudo apt install git-all
```
For other Linux distrubtions, use https://git-scm.com/download/linux.


## Basic Git commands

### Pull from a remote repository
Recall the one of the main aims of using version control is collaborative development. This means that all the collaborators must have access to the project. This is hard to do when the code lives on a personal machine. Thus, in most cases, the code is hosted on a remote server where access can be managed easily.

So, let's say you wanted to contribute a cool feature to someone's code. The first step would be to get their code on your system. Once you access this code on a remote repository such as Github, Gitlab, etc., on the website, clone it to your system. On the command line interfact (CLI), navigate to the folder where you want the repository to be and type: 

```
git clone <REMOTE_URL>
```

Depending on the settings of the repository, you might be asked to first make an account on the site such as GitLab or Github. Do that and repeat this step. You should be able to get the code. Congratulations, you have cloned your first project. 

![some image](https://marklodato.github.io/visual-git-guide/basic-usage.svg)

### Change, add, commit, and push to repository 
Now, make the desired changes to the project. 

Once you have done this, you should want to push these back to the remote repository. This is what we will now do. 

#### Stage
Loosely speaking, when you pulled the repo, the folder that got formed is called the working directory. This contains the changes that you are currently working on. 

Now, we want to "commit" these changes to the history of the development of this project so that they can be retrieved later. 

In order to do this, we must first "stage" these files; i.e., prepare them for being "committed". (I am skipping a lot of details here but i have provided references). To stage all the changes, type:
```
git add "*"
```

#### Commit
Now, we will commit these to our local branch. 
```
git commit -m "COMMIT MESSAGE"
```
Check if the commit has been successful using:
```
git log
```
This shows you a list of the all the commits on the branch. 

#### Push
Let's say we want to push these changes now to the remote repository.

Note that in this case, we assume that the remote is pre-configured in the repository. Be sure to check this using.
```
git remote -v
```
This will show you the information of the remote that the repo is pointing to. Once you ensure that this is correct, type: 
```
git push
```

Depending on the remote, you might be asked for your credentials. Enter those. 

Congratulations! You have finished the basic steps to pull from and push to code to remote repositories.

### Make and manage branches

### Compare branches

### Merge branches

### Configure settings for project



## References
1. Chacon, S. and Straub, B. [Pro git](https://git-scm.com/book/en/v2), 2014.
2. Burgess, A. [Easy version control with Git](https://code.tutsplus.com/tutorials/easy-version-control-with-git--net-7449), 2009. 
3. [A visual Git reference](https://marklodato.github.io/visual-git-guide/index-en.html)
4. Working directory definition https://stackoverflow.com/questions/36201342/git-where-exactly-is-the-working-directory. 
5. Staging: Crunchify https://crunchify.com/git-repository-what-stage-means-in-git-source-control/.
6. Staging: GeeksforGeeks https://www.geeksforgeeks.org/staging-in-git/. 

<!-- 
## GitLab CI

This project's static Pages are built by [GitLab CI][ci], following the steps
defined in [`.gitlab-ci.yml`](.gitlab-ci.yml):

```
image: alpine:latest

pages:
  stage: deploy
  script:
  - echo 'Nothing to do...'
  artifacts:
    paths:
    - public
  only:
  - master
```

The above example expects to put all your HTML files in the `public/` directory.

## GitLab User or Group Pages

To use this project as your user/group website, you will need one additional
step: just rename your project to `namespace.gitlab.io`, where `namespace` is
your `username` or `groupname`. This can be done by navigating to your
project's **Settings**.

Read more about [user/group Pages][userpages] and [project Pages][projpages].

## Did you fork this project?

If you forked this project for your own use, please go to your project's
**Settings** and remove the forking relationship, which won't be necessary
unless you want to contribute back to the upstream project.

## Troubleshooting

1. CSS is missing! That means that you have wrongly set up the CSS URL in your
   HTML files. Have a look at the [index.html] for an example. -->

<!-- [ci]: https://about.gitlab.com/gitlab-ci/
[index.html]: https://gitlab.com/pages/plain-html/blob/master/public/index.html
[userpages]: https://docs.gitlab.com/ce/user/project/pages/introduction.html#user-or-group-pages
[projpages]: https://docs.gitlab.com/ce/user/project/pages/introduction.html#project-pages -->
