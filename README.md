# Learning Git

## What is Git?

- Open source, free source control management or what's referred to as SCM
- With Git, you can manage changes to files over time and you can go back and see what those changes were
- We can revert back to previous versions
- Compare differences between different versions
- See who changed what

You can use any terminal to interact with Git

Open Git Bash
First we need to configure a few things, first of all we need to specify your name and also your email address
	• The reason this is so important Is anytime you commit something or write something to the history book, we need to know who's doing it

First lets specify the name,
```bash
 Git config --global  user.name "Fayas P"
```
Set email address with  

```bash
git config --global user.email fayas@test.com
```

Use -h for help along with any command

or try git help <command> opens up a HTML page that is hosted on your computer

We have the files that make up the sample Kevincookiecompany website and we want to use git to track these files
	1. We ```cd``` to the directory where the files are located
	2. And type in command ```git init``` it has now initialized

We will see that it has initialized the repository for that directory

![image](https://github.com/fayas1290/Learning-Git/assets/157561213/4e068334-b6a6-4763-ac0a-bc3c5533a572)

A hidden file called '.git' is created in the directory and it contains all the necessary repository files

Command ```git status``` tells us the status of our repository

![image](https://github.com/fayas1290/Learning-Git/assets/157561213/5aa85e5e-9dbd-454a-b900-31896fab93ae)

We see that we are currently in the main bracnh

We can see all the files in the directory are untracked, meaning if we make any changes to these files, git wont care because they are untracked

If we track a file git will know what changes are made to that file, if we want to revert back to a previous version, we can do that

How to track a file?
```bash
Git add <filename>
```
We don’t need to add whole path, just filename

To confirm it is tracked, we could use `git status` command

![image](https://github.com/fayas1290/Learning-Git/assets/157561213/511d6199-2d52-4afb-811e-d557699127d2)

If want to no longer track a file
```bash
Git rm --cached<filename>
```

We can also tell Git to ignore certain files, folders or extensions (Here we shall tell git to ignore the Employees Salaries.txt file)

We go to the directory and create a file called  '.gitigonre' (use create new text document option)

We open that file in notepad
Type in comment #ignore all .txt files

To see comprehensive list of how to ignore files, folders and extensions go to website

This is ideal for things like log files and auto-generated files that you don’t want to include as part of your project![image]

To track all files in the directory
```bash
Git add --all
Git add -A
Git add .
```

We added all files from sample and all these files are now in an environment called staging!

And now we shall commit them, what does it mean to commit?

To commit, we are taking a snapshot of your repository at this point in time, basically what all of your files look like right now.  In a sense, its like writing an entry into a history book and if you ever want to go back to this point in the future, you can do that!


To commit, we can use
```bash
 Git commit  -m "first commit - commiting all files to the repository"
```
We added a message with the commit 

We just did our first commit,

There is now a page in the history book

![image](https://github.com/fayas1290/Learning-Git/assets/157561213/adeefa53-6788-4048-b5a1-6ef8bc1bb405)

These files are now officially part of the git record

Now if we modify one of the sample files , we modify index.html by opening it in notepad

We changed text from "egg from chicken that listen to classical music" to "eggs from chicken that are free range"

Now if we enter command git status  we can see following output

![image](https://github.com/fayas1290/Learning-Git/assets/157561213/af627d00-059b-4322-ab33-5917017d2e27)

Git recognises that one of the files has been modified, to see what is modified,
```bash
Git diff
```
This will show us what the differences are

We need to add the file again to the 'Staging', by ```git add index.htm```

Staging is a place where your files sit until you are ready to commit them

In git you have three different environments
	1. Working files
	2. Staging
	3. Commit
	• Adding as a log or an entry into the history book

To remove the file from staging 
```bash
Git restore --staged <filename>
Git restore --staged index.htm
```
This moves our files back to our working files, now if we commit this file will not be included


Lets say you are working on 6 files, you  are ready to commit 3 of them, then we can add them to staging and commit them and leave the other three in the working files status

We can bypass staging altogether as well, and commit
```bash
Git commit -A -m "updated text to free range"
```

We can delete file from git bash 

```bash
Git rm <filename>
Git rm "secret recipe.htm"
```
Use " if filename has space

Here we remove file called secret recipe.htm, 

We can restore a file by
```bash
 Git restore <filename>
```

Files also can be renamed
```bash
Git mv "KCC logo.png" "Primary Logo.png"
```

To review all the commits made
```bash
Git log
```
![image](https://github.com/fayas1290/Learning-Git/assets/157561213/65bfd2f6-acfe-4314-98aa-0a9b8d992630)

Every commit has an unique identifier
We see author, email, date of commit
![image](https://github.com/fayas1290/Learning-Git/assets/157561213/bf7b0b1f-1b4e-4605-8a9b-dd56ea95a6a7)

The following command gives abbreviate version of the above view
```bash
Git log --oneline
```

To change a previous commit message
```bash
Git commit -m "<message>" -amend
```

To see all of the changes in detail in each commit
```bash
Git log -p
```

Git log has all sorts of advanced capabilities
	• You could search for specific test
	• Look for changes that happened before a certain date or even after a certain date

We can always go back to a specific version by 
```bash
	• Git reset <hashtag>
```
![image](https://github.com/fayas1290/Learning-Git/assets/157561213/bd29d2bc-33f0-4c33-a60b-1ff9162868d3)

You can also modify what appears in the log and the order they appear, with something called 'rebasing'
```bash
Git rebase -I --root
```
This brings us to an editor

![image](https://github.com/fayas1290/Learning-Git/assets/157561213/f6823562-f097-49c8-bad1-363433c60146)

So far we have been making changes to our main branch, but we can also set up additional branches

Another branch is basically a copy of your main branch it has all the same entries in that history book
This allows you to go and work on a feature, may be you are fixing a bug and you can make all your changes but it wont affect the  main branch, once you are satisfied with the changes, you can merge it back to the main branch 

This is also how software development typically works, you have developers, may be one is working on a new feature, they will create one branch to work on that feature, someone else who might be working on abug fix might create another branc, once they are done and satisfied with how it looks they can merge that back into main


In the simple ingredients.htm we want to make a change, for that we create another branch,  we need to fix the temperature of oven

To create a new branch
```bash
branch <name for the branch>
Git branch FixTemp
```

To see all the git branches
```bash
Git branch
```
![image](https://github.com/fayas1290/Learning-Git/assets/157561213/1d835fb5-5e9a-46cf-9983-d2f88857d183)

Here we can see there are two branches, FixTemp and Master


To switch to a branch
```bash
Git switch <branch name>
```
![image](https://github.com/fayas1290/Learning-Git/assets/157561213/a45d037a-ab23-4ccd-a2d6-35aa8181ccc6)

Above we can see that the FixTemp branch is selected

We go to the secret recipe.htm file and update temperature to 375F

But when we change the branch back to 'master' we can see the secret recipe file has changed'

When we switch to a particular branch all of the files reflect the current state within the main branch

To merge changes made on FixTemp to master
```bash
Git merge -m "merge FixTemp back to main" FixTemp
Git merge -m"<message>" <the branch that needs to be merged to current branch>
```	
	
We do not need the fixedtemp branch anymore as the data has been merged
We delete it by
```bash
Git branch -d fixtemp
Git branch -d <branch name>
```

What if we created a branch and then we tried to merge it back in, but main has changed since we created our branch, in that case we will have a merge conflict. 

To see how that works, lets create another branch

This command not only switches me to new branch, but also creates the new branch
```bash
Get switch -c UpdateText
Get switch -c <branch name>
```

Now we shall make changes to text in index.htm (changed text from finest ingredient to best ingredient) after switching to the new branch

We commit the new changes, move to master and make a change there as well

We go to index.html and change text (from finest ingredient to the most amazing ingredient)

Lets now update text form UpdateText back to main to see what happens
```bash
Git merge UpdateText
```

We get the following error:
![image](https://github.com/fayas1290/Learning-Git/assets/157561213/a8da3590-229b-4eaa-8069-db105ae14d97)

Also we are in currently in a branch called master|MERGING

We go to file explorer to fix the conflict, we go to index.htm file where we had the conflict

Once we open it, we can see a title called HEAD, it refers to what is currently in master, and down below we can see the text that we are trying to bring in from the branch UpdateText, we can decide which one we want to keep, 
![image](https://github.com/fayas1290/Learning-Git/assets/157561213/245e9d2e-56b7-49f8-ba02-d269ae50b0e1)

Here we want to keep the updated text so we delete HEAD

Now we commit the change and we can see the conflict has been resolved, we are no longer in the conflict|MERGE branch, this is one way to resolve conflict


This is the typical flow that most people use in git, you have some feature or bug that you need to work on, so first you will create another branch, then you will go in and make all of your changes then you can merge It back into the main branch, once you do that you will delete the branch that you have been working on

How do you work together and collaborate with others?

We can also host our git repository in the cloud, one of the most popular git repositories is called GitHub
	• We can store your repository in the cloud
	• You can also manage you project
	• You can set up kanban boards
	• You can track issues
	• You can assign features or bugs to different people
 	• A social coding website


We create GitHub account

We can set it private or public
```BASH
Add gitignore file
Add desc
Add readme
```

push an existing repository from the command line
```BASH
git remote add origin https://github.com/fayas1290/kevincookiecompany.com.git
```

The above command establishes remote connection with GitHub, we are calling this remote connection origin that’s common name people use

Next command will set target branch to main
```BASH
git branch -M main
```

We push all content form local repo to the cloud
```BASH
Git push -u origin main
Git push -u <url name> <branch>
```

We can see that all files of the main (previously master) branch has been pushed to GitHub

![image](https://github.com/fayas1290/Learning-Git/assets/157561213/1cd080c6-3dd7-4dbd-b9f6-ead5229ccb0b)


But only the main branch is preset in GitHub

We can push all branches with
```BASHH
Git push --all
```

GitHub has both branches now

We can click on each file and preview what that file looks like

We can see what the last change was for a file by clicking on the commit message
![image](https://github.com/fayas1290/Learning-Git/assets/157561213/769f93aa-ecfc-4fd4-baac-7ec607271b9f)

We can see the change made to that file,
![image](https://github.com/fayas1290/Learning-Git/assets/157561213/9dcb7a1e-506d-489f-b5b0-5ac9caf7b8a2)

To add a file to GitHub, we can drag and drop or click on Add File

To edit a file, click on the file and click on edit icon
After edit we can click Commit directly on GitHub


![image](https://github.com/fayas1290/Learning-Git/assets/157561213/566fa6f4-ade3-404c-bfc4-4aecad203483)

lick on Gear icon to make following changes
![image](https://github.com/fayas1290/Learning-Git/assets/157561213/4cdc0915-038d-4956-8dc4-70d42f68cfcc)

On the GitHub page there are many tabs on top
We can use Issues tab to add issues, add labels to it, assign it to someone and others can comment on it, discuss about it


![image](https://github.com/fayas1290/Learning-Git/assets/157561213/23225c20-90e4-4395-99c0-1536e6e5d9b6)

Use softwrap to see all text on screen
![image](https://github.com/fayas1290/Learning-Git/assets/157561213/a381601f-1aef-4947-ba0f-e334d981c6a6)

While committing in GitHub, we can either connect directly to the main branch or we have the option to commit the changes to a new branch and to start a pull request

What is a pull request?
We can start a pull request and the change has to be approved, If we are working with others, we can have other people go in and make changes and you can have them submit a pull request so the change has to be reviewed by someone before you push it through the main branch

![image](https://github.com/fayas1290/Learning-Git/assets/157561213/ae3140ea-59d4-4717-9eef-803d261b847c)

Once we have created the pull request, we can comment on it, discuss merits of the change in a box below, you can merge the pull request also tie it an ISSUE (we created before)

Now if merge the pull request and confirm not only will it merge back to main, it will also close out the corresponding Issue


Up at the top there are a few more tabs, theres one called Actions, this is where you can run tests, you can basically write programs to manage your repository

Projects
	• Project management view where you can view all of your issues, pull requests, filter the different views, it makes it really easy to manage your projects

Wiki
	• This is where you can document your code
	• Kind of like Wikipedia for your project

Security
	• This is where you can manage all your policies
	• You can define what should happen when a vulnerability is discovered
	• Set up scanning

Insights
	• You can see who's contributing to your project
	• What does the traffic look like
	• How many issues have been closed
	• How many commits have there been

Settings > collaborators
	• Add additional people to work with you on your project

In the main repository view
On the RHS, we can create a release
![image](https://github.com/fayas1290/Learning-Git/assets/157561213/cc09828e-778f-460c-9bc3-dbe08e2ff401)

We can choose a tag called 'release' and version number for our website
![image](https://github.com/fayas1290/Learning-Git/assets/157561213/52054151-93e1-47d3-acf6-de360ffc2614)

Once a release is created we can see the source code under it

![image](https://github.com/fayas1290/Learning-Git/assets/157561213/6b5b6096-9d92-4cbb-861a-53490514f8b1)

We made some changes on the GitHub on the cloud, how do we bring those changes  back to our PC?

There are  different commands for this
	1. ```Git fetch``` - this will download all the chnanges from remote tracking branches
	2. To merge that in we can do Git merge that will now merge it in on what we have on our machine

Instead of typing these two commands we can also type in 
```Git pull``` - this combines fetch and merge into one command

---
<BR>
<BR>

Pull requests are always based on branches and not individual requests

When file was modified in one branch and deleted in another git conflict happens

Undo merge conflict by
```BASH
Git merge --abort
```

Git marks conflict problem area in text like files with >>>>>> and <<<<<
![image](https://github.com/fayas1290/Learning-Git/assets/157561213/2446dd8e-d3ef-436d-8007-fb515ccf0b6a)


The problem that come after the first marker (<<<<<< HEAD) originates from our current working branch

The equal  signs separate the two conflicting changes, here in develop branch the text that is shown under HEAD was deleted, and changes were made in the text in HEAD branch so git was unsure did you wanna change them or delete them? That is the conflict

Look at this example for more clarity, here text was edited in HTML file between two branches

![image](https://github.com/fayas1290/Learning-Git/assets/157561213/d791d5e8-1bb1-40c0-b99a-c0893b91bea2)

We can see the changes separated by equal sign 

The following command can be used to bring up a GUI merge tool that shows difference made in each branch and the final output that we need to keep, 
git mergetool -g --tool=kdiff3

Example is below, Kaleidoscope merge tool in Mac

Merge Vs. Rebase

Rebasing makes all commits included in the main branch, even though there was a separate branch created and commits were made in that branch. Upon rebasing the commits made in new branch are also included added to the main branch as opposed to while merging two branches
![image](https://github.com/fayas1290/Learning-Git/assets/157561213/e8bc5288-d50a-48b6-b9cf-c3e39fa144ac)





