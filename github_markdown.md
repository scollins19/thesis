## Assignment 6 , Sarah Collins 14309361

### Using GitHub

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

The <b> -m </b> flag was used to pass a message for the commit, which includes any changes made. If you don't pass a message, a text editor will open an ask you to input a message.

To view the record of your commits, use:

<code> git log</code> :

commit b1fe4d08f997f9a7437488da766c99f19464548d
Author: scollins19 <saraheileencollins@hotmail.com>
Date:   Wed Nov 28 10:26:10 2018 +0000

    Add initial version of thesis code.



For each commit, it lists the unique identifier for that revision, author, date, and commit message.

The commit identifier is useful as it can be used to differentiate between two files, restore a file, and retrieve tracked filed if they are deleted.

Now you are free to make changes to the files knowing that you can  always revert them to the state of this commit by referencing its identifier. As an example, edit <code>clean.py</code> so that the fold change cutoff for filtering peaks is more stringent. Do this by opening the file in a text editor and save the changes made.



<b> Editing </b> 

So now, Git is tracking <code> clean.py </code>. So if we use the command <code> git status </code> again,  it will show us that this file has been modified, but has not been sent to be stagged.

To view the unstaged changes, we can run the command:

<code> git diff </code>

This will show any lines that have been added or removed in the file marked with a <code> a+ </code> or <code> a- </code> respectively.

To undo the edit, use the command:

<code> git checkout -- clean.py </code> 

If several changes were committed to the file and you wanted to revert back to the original file, you can input the commit identifier that was made from the first instance of commit. This can be accessed using the git log function again, then taking the first seven characters of the identifier. 

<code> git checkout b1fe4d08 clean.py </code>



<b> ASIDE </b>:

<b> git log  output</b>

commit 529713a67c5ac19a2d9df9170a41c6c3c4ea30b8 (HEAD -> master)
Author: scollins19 <saraheileencollins@hotmail.com>
Date:   Wed Nov 28 17:26:19 2018 +0000

```
markdown
```

commit b1fe4d08f997f9a7437488da766c99f19464548d
Author: scollins19 <saraheileencollins@hotmail.com>
Date:   Wed Nov 28 10:26:10 2018 +0000

```
Add initial version of thesis code.
```



<b> git diff  output</b>

diff --git a/clean.py b/clean.py
index 9f76681..7f7ccf1 100644
--- a/clean.py
+++ b/clean.py
@@ -28,7 +28,7 @@ def filter_fold_change(feature, fc = 1):
​         return False

Filter based on fold-change over control sample

-fc_cutoff = 10
+fc_cutoff = 20
 epithelial = epithelial.filter(filter_fold_change, fc = fc_cutoff).saveas()
 proximal_tube = proximal_tube.filter(filter_fold_change, fc = fc_cutoff).saveas()
 kidney = kidney.filter(filter_fold_change, fc = fc_cutoff).saveas()



<b> NOTE </b>: Once the clean.py file was reverted back to the original, the output of <code> git diff </code> was empty 





### Share your code

Now we can share our Git repository online. To do this, first we must make an account on Github, and use the option 'Create directory' on the homepage to make a directory called 'thesis'.

This will then produce a path URL to the repository that you should copy. 

'https://github.com/scollins19/thesis.git'

Back in the terminal, we want to add this repository and name it so we don't have to produce the path to the online repository every time we want to push files to it. Use this using the command:

<code> git remote add origin https://github.com/scollins19/thesis.git  </code>

Now we can send our files from our local repository using the command:

<code> git push origin master </code> 

This will send the files to our online github repository.



<b> Accessing Github from multiple machines </b> 

If we wanted to work on your code from home, the Git repository can be downloaded using:

<code> git clone https://github.com/scollins19/thesis.git  </code> 

By default, this will download the Git repository into a local directory named “thesis.”  Your changes can also be pushed back to GitHub easily as the remote 'origin' will automatically be added.

On the original computer where you set up the git repository, you can then update the code with the changes made from the home

Then the next day back at your work computer, you could update the code 
with the changes you made the previous evening using the command :

<code> git pull origin master </code>

This allows for a network to be created between your home computer, work computer and the online GitHub account so you can easily share code online and edit it with ease.



<b> URL to GitHub account </b>

https://github.com/scollins19