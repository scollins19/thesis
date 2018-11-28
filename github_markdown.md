While many GUIs exist for Github, it is useful to know how to use it from the command line. 



Installing Github:

<code> sudo apt-get update </code>

<code> sudo apt-get install git -y </code>



For this tutorial, we must make a folder within our home directory called 'thesis'

<code> mkdir thesis</code>

In order to allow Github to know who is making changes to the files, you need to provide information of yourself. 

Firstly, provide your name: 

<code> git config --global user.name "scollins19"</code>

Followed by your email, 

<code> git config --global user.email "saraheileencollins@hotmail.com" </code>



Now we can begin to version our code. 

The files 'codes.tar' have been downloaded into the 'thesis' directory that was just made, but we need to untar the to actually be able to work with them. To untar we must change the directory to the 'thesis' folder where the files are located. 

<code> cd ~/thesis </code>

<code> tar -xvf codes.tar </code> 

In order to begin versioning code with Git, we need to set up a Git repository within this directory by running:

<code> git init </code> 

Once this is complete, we can begin to utilize Git to save alterations that we save to our scripts, but only when we command it to. To see what Git is doing as you record your files, run:

<code> git status </code> 

From this, we can only see our file names in red, meaning that no files have been presented to the staging area to be committed.  

So we want to include the rest of the files to the repository:

<code> git add process.sh analyze.R clean.py </code> 

If we run the git status command again, these files have now been added to the 'changes to be committed', and are now being tracked. 



<b> Commit </b> 

Now we can begin to commit to these files. 

<code> git commit -m "Add initial version of thesis code." </code>

The <b> -m </b> flag was used to 

Notice the flag -m was used to pass a 
message for the commit. This message describes the changes that have 
been made to the code and is required. If you do not pass a message at 
the command line, the default text editor for your system will open so 
you can enter the message



