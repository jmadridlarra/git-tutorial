# git-tutorial
A quick tutorial for how to use git!

This tutorial assumes no knowledge of git, but does assume knowledge of command line interfaces. 

**What is git?**

Git is a version control software that allows users to revert files back to older versions.  Git accomplishes this by saving checkpoints called "commits" and allows the user complete control over what will be saved at each checkpoint. Additionally, multiple users can work on different facets of the same project and then get automatically merged (...kind of) together when needed. Additionally, there are many graphical user interfaces (like [gitkraken](https://www.gitkraken.com/)) that allow git usage for non-coders as well!

# Git basics

1) **Install git** - Visit the [git website](https://git-scm.com/downloads) and download the correct distribution for your computer. You can follow [this tutorial](https://phoenixnap.com/kb/how-to-install-git-windows) for step by step instructions for how to download git. I reccomend using git BASH which the above tutorial details how to set up for your computer.  
2) Now that you have downloaded git you can open your terminal or git BASH distribution.  
3) Navigate to the folder you want to create your git project in. For this tutorial I've made a folder named git-tutorial. 
4) Then type the following command `git clone https://github.com/jmadridlarra/git-tutorial` 

NOTE: all commands using git in terminal will be proceeded by 'git'. 

`clone` makes a local copy of the git-tutorial and downloads it to your machine.  This effectively creates your *local distribution*. In order to push changes from your local distribution to the remote host, use `git push origin BRANCHNAME`.  Then, to pull changes from the remote repository use `git pull origin BRANCHNAME`. 

5) Now that you have cloned a distribution, type `git status`.  This command shows all the changes you have made.  Since this is a new distribution and we have not made any changes, the status command should not show any files. 
6) Open the `hello.txt` file using the text editor of your choice. Then, change the text...however you want! Save the file and navigate back to your command prompt. Now, type `git status` again.  If you are using git bash, the file path of `hello.txt` should now be red. For all CLIs your file path will now show up under 'changes not staged for commit'. 

Much like clicking save, creating a commit creates a checkpoint for the user to revert back to.  

7) Prior to creating a commit however, you must add your file to the *staging area*. The staging area acts as a collection space for you to collect all the files you would like to include in your commit. In order to add files to the staging area use the `git add PATHNAME` command. Now, type `git status` again.  The file that you added will now turn green (if you're using git BASH) and will show up under the 'changes to be committed' section. You can add as many files as you would like to the staging area to be included in the commit. 

Helful tips: `-a` adds all changed files to the staging area. Specifying a folder as a PATHNAME adds all *changed* files in the folder to the staging area.

8) Now we are ready to create our commit.  Use `git commit` to commit the files.  This should automatically open a text editor and prompt you for a commit message.  The commit message is a brief description of the changes of the files in the staging area.  In other GUI git softwares, users can add descriptions which can be longer, but it is best to keep commit messages brief.  This commit will create a unique ID called the commit SHA-1 checksum.  This allows users to identify specific commits and return back to them. In order to see a list of all commits and their SHA-1 checksums use `git log`. 

Helpful tips: `-m 'COMMIT MESSAGE'` allows a user to type a commit message in the CLI rather than opening an external editor.  

It is important to commit files any time you might want to revert something.  A good rule of thumb is creating a commit every time a new feature is added or changed.  That way, if something gets broken during this change, it is easy to revert back to an older commit prior to the broken commit. 

# Branches

Similar to the way a tree branch breaks off from the trunk, a branch is a new working space based off of the old branch.  Any time you make a new branch it has all of the changes from the old branch, but if you make changes to the new branch, it will not change the old branch. 

1) Use `git branch BRANCH_NAME` to create a new branch titled anything you want.  Then, type `git branch` to see all the branches that exist on your local machine.  
2) In order to switch between branches, use `git checkout BRANCH_NAME`.  Use the *checkout* command to switch to your new branch.  

NOTE: It is important to remember that `git branch` only creates the branch, it doesn't switch to it.  In order to create and switch to a new branch all in one line use `git checkout -b NEW_BRANCH_NAME`

3) You should now notice that the branch name (shown in parantheses after the path) has changed. Now you can make as many commits as you would like in this new branch, without affecting the main branch. Make a change in *hello.txt* and commit it. (`git add PATHNAME` `git commit -m 'COMMIT MESSAGE'`)
4) Now, use `git checkout main` to return to the main branch. 

So now we've made a branch and made some changes to the branch...now what?  Typically projects like to have a tested, working version of their code separate from the fixes and new features they are creating.  These fixes and new features are usually developed in other branches with a naming scheme that has to do with the feature being developed. The 'main' branch is typically a working version of the project.  So how are new features and updates integrated? The `merge` command automatically integrates one branch into another.  

5) Currently, you should be in the **main** branch. By typing `git merge BRANCH_NAME`, you are merging the BRANCH_NAME branch **INTO** the *main* branch. After this merge, the main branch will contain all original changes and any updates from the BRANCH_NAME branch. 

If there is a problem with automatic merging, git will complain and let you know that there is a 'merge conflict'.  Then, git will edit the file to display both versions of the code that is causing the merge conflict. 

