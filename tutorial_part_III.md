# Part III: Merging Branches and Conflict Resolution

## Key concepts

## Merge branches
Now that have compared the two branches to see the difference between them, let us go ahead and merge them. 
First, let us commit our changes. As before, type:
```
git commit -m "Add pseudocode for parking ticket app"
``` 

Conventions for writing these messages are provided [here](https://gist.github.com/robertpainsi/b632364184e70900af4ab688decf6f53). 

Now, let us merge this feature branch into the master branch. First, we must go to the *master* branch which we do using the command:
```
git checkout master
```
Notice that in general, we use `git checkout` to switch between branches (and also files).

Merge the branches using
```
git merge feature/parking_tracker
```
With this simple command, Git should merge your changes into the *master* branch and give you a result which contains the words *Fast-forward*. Check that the file *app_ideas/parking_tracker/pseudocode.txt* has been created using:
```
ls app_ideas/parking_tracker/pseudocode.txt
```
Also check what Git has done by typing:
```
git log
```
You will notice that the commit you made on the branch *feature/parking_tracker* will appear in the commit history on *master*. To read more about what is going on in the background, read this page by [Atlassian](https://www.atlassian.com/git/tutorials/using-branches/git-merge#:~:text=Git%20merging%20combines%20sequences%20of,conflict%20in%20both%20commit%20sequences.).

While this command may seem very easy on the surface, Git can do a lot of heavy lifting in the background if need be. We won't get into all the details here, but I encourage you to read to the [section on Merging](https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging) in Pro-Git. I also encourage you to read the documentation of the `git-merge` command which you can access by typing `man git-merge` in your CLI.  


## Deleting a branch
Now that you have merged your feature branch into the master branch, you don't really need it. Thus, it might be a good idea to go ahead and delete the feature branch to avoid clutter in the branch history. 

Do this using 
```
git branch -d feature/parking_tracker
```
__*Note*__: Be __*very*__ careful while doing this! If you accidentally delete a branch, it can be hard to retrieve. 

Now, go ahead and push this updated repo to Github just as before:
```
git push
```

## Conflict resolution (Under development)
In the previous case, the merge occured without any errors since, we had only added some new files. But what would happen if there were a conflict? This typically occurs if you change the same part of the same file differently in the two branches being merged. In this case, we will resolve the conflicts and merge the branches. 

### Setting up the conflict
First, we need to create the conflict. Let's switch to our feature branch and make another branch from it. Then, we will modify the file *app_ideas/parking_tracker/pseudocode.txt* differently in the two branches. We will then try to merge these. As you might expect, there will be a conflict which we will resolve. Graphically, what we are trying to do looks like this:

```
        ____B2__
       /        \ (Attempted merge)
__B1__/__________\ B1

```
Let's go ahead and implement this. 
```
# Switch to feature branch
git checkout feature/parking_tracker
# Create a new branch
git branch feature/parking_tracker_divergent
```

Now, open up *app_ideas/parking_tracker/pseudocode.txt* in your text editor of choice and add a line to it having the text "*__Some text__*". Save and close the text editor. 
As before, stage and commit this change. 
```
git add app_ideas/parking_tracker/pseudocode.txt
git commit -m "Modified pseudocode one way"
```

Let us switch to the other branch. 
```
git checkout feature/parking_tracker_divergent
```
As before, add a line to *app_ideas/parking_tracker/pseudocode.txt*. Only this time, add the text "*__Some other text__*". 

Add and commit this change just as before but with a different commit message for clarity.
```
git add app_ideas/parking_tracker/pseudocode.txt
git commit -m "Modified pseudocode another way"
```

### Resolving the conflict
Now that we have set up divergent branches, let us try to merge them. 
```
git merge feature/parking_tracker
```
This should give you the error message:
```
Auto-merging app_ideas/parking_tracker/pseudocode.txt
CONFLICT (content): Merge conflict in app_ideas/parking_tracker/pseudocode.txt
Automatic merge failed; fix conflicts and then commit the result.
```
*__Note__*: Sometimes, Git also opens up a Vim editor to prompt the user to enter a commit message. In this case, simply exit the editor by typing `:q`.

What git has done is that it has flagged the conflict. This change hasn't been staged or committed. See this by typing `git status` in the terminal. 

Now, we wish to resolve the conflict. Open the file *app_ideas/parking_tracker/pseudocode.txt* in your favorite text editor and be sure to remove the lines containing.
```
<<<<<<< 
=======
>>>>>>>
```
Decide on which version you want to keep in the last line. Let's say in this case, we decide to keep parts of both. So, let the last line be "*__Some different text__*". The merge conflict has been resolved. 

Let us now stage and commit our merge. 
```
git add app_ideas/parking_tracker/pseudocode.txt
git commit -m "Resolved conflicts and merged branches"
```

Congratulations! You have now resolved conflicts and merged branches. 


## Summary
Congratulations, you have finished Part II of the tutorial. You have learnt the basics of branching. You understood the idea of branching and created, compared, and merged branches. 
