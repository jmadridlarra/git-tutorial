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
6) Open the `hello.txt` file using the text editor of your choice. Then, change the text...however you want! Save the file and navigate back to your command prompt. Now, type `git status` again.  If you are using git bash, the file path of `hello.txt` should now show up under 'changes not staged for commit'. 

Much like clicking save, creating a commit creates a checkpoint for the user to revert back to.  

7) Prior to creating a commit however, you must add your file to the *staging area*. The staging area acts as a collection space for you to collect all the files you would like to include in your commit. In order to add files to the staging area use the `git add PATHNAME` command. Now, type `git status` again.  The file that you added will now turn green (if you're using git BASH) and will show up under the 'changes to be committed' section. 
8) 
9) 
10) 
11) 
12) 
13) 
14) Similar to the way a tree branch breaks off from the trunk, a branch is a new distribution based off of the old branch.  Any time you make a new branch it has all of the changes from the old branch but if you make changes to the new branch it will not change the old branch. By cloning the original repository, you have created a local version 
15) 
