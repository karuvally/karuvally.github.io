---
layout: post
title: Git Quickstart 
---

This is going to be a short and sweet tutorial to get you up and running with
git. Git is a version control system. A version control system keeps track of
file changes. If the current version is not working, we can go back to a
specific version which worked.

If you have ever tried to write a program, you will right away recognize that
having such a system will immensly ease the development process. A version
control system such as git also saves the day when you are working as part of
a team. But right now, let us concentrate on getting our feet wet :)

# Installation
Installing git is easy.

If you are on Debian or Ubuntu derivates

    $ sudo apt-get install git

If you are on Fedora/CentOS

    $ sudo dnf install git

# Creating Github account
Now lets create a Github account. Github is a web service which uses the git
protocol to allow upload, download and sharing of our projects. It is perfectly
possible to use Git without Github. But with Github, all of our code will be
safely backed up and also makes it easy to share our code with others.

Enough lecturing. Go to [https://github.com](https://github.com) and create an
account. Once that is done, create a new repostory (project). A repository is
like a directory which contains all the source files of a particular project.
From now on, we are going to call it a repo. Why? because it sounds cool.

To start working on the repo, we will have to clone it. Cloning means we are
creating a local copy of the repo on our computer. This can be done by clicking
on the "Clone or Download" (green) button on the repo page and copying the URL
to clipboard.

Now open the terminal, navigate to a directory where you want to store the
repo and execute

    $ cd /home/user  
    $ git clone the-copied-url  

Once thats done, you will see that we now have a new directory with the name
of the repo. Lets navigate into the directory and create a README file

    $ cd new-repo-dir  
    $ touch README.md  

We just created a README file, which is used to give a brief introduction of
the project to anybody who visits our project page on Github. The README is in
[markdown](https://daringfireball.net/projects/markdown/syntax) format, follow
the link to learn more.

Now that we created the README, lets commit the file. Commiting is the process
of registering the changes we have made with git. It consists of two steps.
Adding the file, which causes git to start tracking our file and then the
actual commit process.

    $ git add .   

See that . (dot)? It asks git to add all the files in our directory, sparing
you from the task of manually adding each file. Next is the commit command.

    $ git commit -m "the commit message"   

At this point, git would have probably interrupted you asking for your name
and email address. Type it in

    $ git config --global user.name "You full name"  
    $ git config --global user.email yourmail@domain.tld  


Now lets get back to commiting. Execute the commit command again. See the
commit message? it gives a very short info on what actually comprises of the
commit.

Once you start a serious project, commits will start piling up and the commit
message will be your only way to know what comprises of a commit other than
ofcourse manually reading the whole source file :D

Once this is done, we can upload the commit to Github. This is called pushing.
Enter your Github credentials when Git asks for and... it should do the trick.

    $ git push

# Conclusion
Git can do lots of awesome stuff. But right now, this will suffice. Just
remember to do small, frequent commits as this will allow you to easily trace
your code changes.

