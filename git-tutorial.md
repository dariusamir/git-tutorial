# Git tutorial

This tutorial will walk you through the basics of git using the command line. After working through it, you will be able to apply the covered commands to your own projects in the future. For this, you’ll need the Visual Studio Code IDE and Git Bash installed on your device. 

## Repository
First, let’s discuss what exactly the term **repository** entails in Git. A repository can be thought of as a folder that contains all your files for a given project. For this tutorial, you don’t need to create your own. A link to a public repository containing all the relevant files will be provided
## Cloning and Forking
Now, let’s dive into cloning and forking. **Forking** let’s you get your own remote copy of the repository to work on. **Cloning** allows you to get a copy of the repoposity that is remote on your local machine. 
1. Go to this link: https://github.com/dariusamir/git-tutorial
2. Click the **fork** button. It is located towards the top right of the web page, right below the navigation bar. The website will redirect you in some time to a new page where you will see your username displayed in the url. You have now created your own copy of the repository. Now, we will move towards cloning.
3. Click on the green **code** button. Make sure you are on the HTTPS tab within the mini popup. Copy the link displayed here.
4. Open Git Bash and navigate to the directory you would like to work on using the command line navigation commands.
5. Type in the following command. Replace LINK with the link you copied earlier in step 3.
```
git clone LINK
```
6. You will now have a local copy of the repository called **git-tutorial**. Navigate to it using Git Bash. 

## Branches
Now, let’s get into creating a new **branch**. Branches let us add and edit code from the main repository. They help us ensure that we don’t edit the main initial code until we are ready to do so. Branches allow for safe experimentation and let us have our own space in a repository that other users may be using as well. The initial branch is called the **main** branch.
1. To create a branch, type in the following command in Git Bash. Replace the branch-name with whatever you wish to name your branch. 
```
git branch branch-name
```
2. Switch to using this branch by typing in the following command. You should now get the message, “Switched to branch ‘branch-name’”
```
git checkout branch-name.
```

## Stashes
**Stashes** enable us to shelf changes we make on our local files so that we can work on something else temporarily. These stashes will always be available for us to reapply once we are ready for them.
1. Go to Visual Studio Code and open the git-tutorial folder. 
2. Click on the HTML file. It is called git-tutorial.html. Save your file.
3. Type in the following 
```
<p> Hello World </p>
```
4. Go back to git bash and type in the following command
```
git stash -a
```
5. To illustrate how stashes work, we will actually go ahead and delete the HTML file that you just edited.
6. Now, create a new CSS file called “git-tutorial.css”
7. Change the color of the background to whatever you wish using the following code. Feel free to replace the already provided hex-code with your own choice. Save your file.
```
body{ 
background-color: #E5FCFF;
}
```
8. Go back to Git Bash and type in the following command. The output will show you the stashes you currently have. 
```
git stash list
``` 
9. Now, type in the following command to apply the stashed changes to your project again.
```
git stash pop
```
You should be able to see the HTML file appear in your git-tutorial folder again. 

## Adding and Committing
Now, we will make some more changes to our local file and create a new one. 
1. Go to the git-tutorial.html file again.
2. Add the following line of code on the top. This will help us apply the changes from the git-tutorial.css file to the html file. 
```
<link href="git-tutorial.css" rel="stylesheet" type="text/css">
```
We are done making the necessary changes, so let’s move on to **adding** and **committing**. Adding allows modified and newly created files to be moved to the staging area of Git. Think of the staging area as a space representing a rough draft of whatever it is that you are working on. Committing allows for the snapshotting of specific changes or sets of changes in a Git project. 
1. Go back to Git Bash and type in the following command.
```
git add -A
```
2. Now type in the following command. 
```
git commit -m “Added a css file and modified the html file”
```
3. Finally, type in the following command. The output will be 
```
On branch branch-name nothing to commit, working tree clean
```


##Pushing
**Pushing** lets us push the changes we made onto our local repository. To do this, just type in the following command, making sure to replace the branch-name with whatever else you chose to name your branch. 
```
git push --set-upstream origin new-branch
```

## Updating the Local Repository
Since multiple people can use remote repositories, it is important to make sure the changes are synced for your fork. 
1. Copy the link of the original repository by doing the things highlighted in step 3 of the **Cloning and Forking** section. 
2. Type in the following command on Git Bash. Replace “LINK” with the link you copied.
```
git remote add upstream LINK
```
3. Now type in the following command. You should get an output that shows you the links for the original and your own fork of the repository.
```
git remote -v
```
4. Finally, type in the following. This will help get commits from the remote repository onto your local one. 
```
git fetch upstream
```

## Merging
**Merging** lets us merge the changes made in the new branch with the main branch. This ensures that our changes are actually applied back to the original branch. 
1. Switch back to using the main branch in Git Bash. Use the checkout command introduced in the **branches** section of this tutorial. 
2. Now, just type in the following command 
```
git merge upstream/main
```
Now, all the changes that were made in this tutorial are merged with the main branch. 

## Pull Request
Finally, a **pull request** is used to ask the original creator of the original repository to merge the code with the project. Although no one will be responding to your pull request for this tutorial, it is still good to practice. 
1. Navigate to the **Pull requests** tab on your repository on github. 
2. Click the green **New pull request button**
3. On the next page, choose the appropriate branches. Choose a title and description. Finally, click the **create pull request button**.
