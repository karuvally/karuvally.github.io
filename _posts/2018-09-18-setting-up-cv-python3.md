---
layout: post
title: Setting up OpenCV with Python 3
---

Things change. Half an year ago, I was happy with running OpenCV on Python 2.
But not anymore. As hard as it is for me to admit, it is time to switch to
Python 3. So here is my supposedly easy to follow tutorial on setting up OpenCV
on Python 3.

# Prerequisites  
First of all, get the latest package listings from the repository. If you are
on Fedora, you can safely skip this. If you are on Debian, do the following.

    $ sudo apt-get update

If you are Fedora, you can safely skip this step.

With this post, we are dealing with the Python 2 side of things. so make sure it is installed. On Debian derivatives, you can just do  

    $ sudo apt-get install python  

If you are on fedora,  
    
    $ sudo dnf install python27  

Once that is out of our way, we need to install the Python package manager, pip. On Debian derivatives, do  
    
    sudo apt-get install python-pip

On fedora, you can do
    
    $ sudo dnf install python-pip

Now we proceed to install Virtualenv.  

# Setting up Virtualenv  
Virtualenv is a container inside which you can set a Python environment complete with libraries which is independent from the rest of the system. Setting up Virtualenv is worth it, as it won't interfere with the rest of your system and will continue to work after a distro hop. Now that we have pip on our system, installating Virtualenv is as easy.

On fedora, do
    
    $ sudo dnf install python2-virtualenv 

If you are on Debian, do
    $ sudo apt-get install python-virtualenv

Once installed, go to someplace where you want to keep the files for your project. Create a directory for the same and initialize a virtualenv inside the directory. It is done as follows.  
    
    $ mkdir opencv  
    $ cd opencv  
    $ virtualenv .  

To make a virtualenv work for us, we need to activate it. This is done by calling the activate script.  
    
    $ source bin/activate  

Once this is properly done, your prompt should change to something that resembles  
    
    (opencv) $  

Okay. Thats it. Lets move on.  

# Installing the libraries
Now we address the elephant in the room. Let us setup OpenCV and some of the essential packages to make it work for us.  
    
    $ pip install opencv-contrib-python # the OpenCV package  
    $ pip install imutils               # convinience functions  
    $ pip install matplotlib            # easily plot the resultant images  
    $ pip install jupyter               # easy, powerful programming environment
    $ pip install numpy                 # for managing all those image arrays  

# Lets code!  
If you want an easy to use programming environment for learning OpenCV, you just installed it. We are ofcourse, talking about Jupyter Notebook. To start, do  

    (opencv) $ jupyter notebook  

As always, once you are done coding, you can quit by presssing "Ctrl + C", then
deactivate Virtualenv by running "deactivate" command 

    (opencv) $ deactivate

