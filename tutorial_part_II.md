# Part II: Introduction to Branching
In this tutorial, we will cover the basics of branching such as making and managing branches. 

## Branches
Concisely ([Pro Git](https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell)), 
> Branching means you diverge from the main line of development and continue to do work without messing with that main line. 

A line of development can be thought of a series of commits where changes are made progressively. 
Branching can be used for various purposes, such as feature development, collaboration, etc. 

Here are two cases related to our project where that might be useful: 

1. *Feature development*: Say you were developing a cool new app idea but aren't finished with it yet. You don't yet wish to merge it with the main code.

    How do you do it? Develop your new idea on a separate branch and then merge it with the main one when you feel ready. 
    
    *__Convention__*: In fact, during development, it is recommended that you make new changes on a `dev` branch, test it thoroughly, and only then merge it with the `main` branch. 

2. *Collaboration:* Recall that that one of the goals of version control was to allow collaboration between developers. When you work on the code on your machine, you work on a branch of it; i.e., your local branch. Other developers work on their local branches and eventually, the changes are combined. Git gives you a great deal of control over how these changes are merged. More on this [later](#contributing-to-open-source-projects). 

Now,let's actually play around with code branches.

### Make and manage branches
#### Making branches
First, let's see which branches we currently have. In our CLI, let's type
```
git branch --list
```
This should list the branches available. The branch that we are on, is prefixed with a *\**. At this point, I get the output:
```
* master
```
Chances are that you will get something similar as the default branches are often named *master* or *main*. 

Let's say you wanted to create a new feature called *Parking tracker* which tracks parking in the area. Let's go ahead and create a new branch using: 
```
git branch feature/parking_tracker
``` 
Let's see what happened. Type:
```
git branch
```
You should see something like this:
```
* master
feature/parking_tracker
```
This means that you have successully created a new branch. Notice that you were able to have `/` in the branch name. This is a useful convention when having different branches since it let's you specify what the branch is for; i.e., a feature, bug fix, long-term development (WIP), etc., and some identifying text. This makes managing branches much easier. 

Now, let us switch to this new fabulous branch. Type:
```
git checkout feature/parking_tracker
```
Again, typing,
```
git branch
```
You should should see:
```
master
* feature/parking_tracker
```
Indicating that you have successfully switched branches. Congratulations! 

#### Making some changes
Now, let us make some changes to add this new feature. Let's create a new directory. 
```
mkdir app_ideas/parking_tracker
```
As before, create a new file called, *pseudocode.txt* and write some lines about how you will create this app. 

Great, you have developed your new app idea. Let's now share it with the world! 

### Compare branches
Let us take a status check. As before, type:
```
git status
```
This should show you something like this:
```
On branch feature/parking_tracker
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	app_ideas/parking_tracker/
```
As before, let's stage these changes for commit using 
```
git add *
```
Now, let us compare what we have in this branch (working tree) with the *master* branch from before. Type
```
git diff master
```
Git will show the differences between our two branches. To exit, simply type `q` in the CLI. 

You might notice that the format in which these differences are shown can be overwhelming. Also, it doesn't help that the differences aren't shown side by side which is intuitive. To solve this, type:
```
git difftool --tool=vimdiff master
```
This will show you differences side-by-side, file-by-file, in a much more manageable way. When you wish to exit the *vim* editor, simply type `:q` in the console. 

__Note__: There are a few other tools available to show differences, but I am a fan of [Vim](https://www.vim.org/about.php) and like to use *vimdiff*.

__*Result:*__ Anyways, you should see that the difference between these two branches is that the file *parking_tracker/pseudocode.txt* was added. This is the change that you made. 

So, congraulations! You are now able to create branches, modify them and compare them. 