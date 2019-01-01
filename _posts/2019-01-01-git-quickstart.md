Topics
------

This is going to be a short and sweet tutorial to get you up and running with
git.

git is a version control system. A version control system keeps track of file
changes.

If your current version is not working, you can go back to a specific version
which worked.

If you have ever tried to write a program, you will right away recognize that
having such a system will immensly ease the development process.

You can hack away on your code without worrying about ruining stuff that
currently works.

Want to restore function that you deleted because you felt like doing it? You
can do that too.

But most importantly, you will leave a trail of whatever you have been doing
with the code. Making the it easier to develop and fix stuff.

The features and advantages a version control system provides does not end
there. But right now, let us concentrate on getting our feet wet :)


Installing git is easy.

If you are on Debian or Ubuntu derivates
    sudo apt-get install git

If you are on Fedora/CentOS
    sudo dnf install git

Just to confirm, type git in the terminal and you will be showered with lots
of text.


Okay. lets create our first repo. A repo is created in the directory we are
planning to store our code.

Let us create a directory named "project" and cd into it
    $ mkdir project
    $ cd project

Let us create the actual repository
    $ git init



