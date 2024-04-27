![image](https://github.com/fayas1290/Learning-Git/assets/157561213/1d5cb78a-1d37-4e0e-a242-96bac7882d91)# Learning Git

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
