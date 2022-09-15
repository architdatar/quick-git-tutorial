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

## Conflict resolution (Under development)
In the previous case, the merge occured without any errors since, we had only added some new files. But what would happen if there were a conflict? 


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

## Summary
Congratulations, you have finished Part II of the tutorial. You have learnt the basics of branching. You understood the idea of branching and created, compared, and merged branches. 

