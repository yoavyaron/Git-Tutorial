# Git & Github Tutorial

## Command line

### Basic Commands
 - `pwd [-LP]`
 - `cd [-L|-P] [dir]`
 - `ls [-ABCFGHLOPRSTUWabcdefghiklmnopqrstuwx1] [file ...]`
 - `mv [-f | -i | -n] [-v] source target`
 - `touch [-A [-][[hh]mm]SS] [-acfhm] [-r file] [-t [[CC]YY]MMDDhhmm[.SS]] file ...`
 - `mkdir [-pv] [-m mode] directory ...`

### File Organization

The current directory is denoted by a dot (`.`). The parent directory is denoted
by two dots (`..`). To go up a directory you can type `cd ..`. To list the files
in your current directory you can type `ls .`, which can be shortened to just
`ls`.

## Git

### Create a repository
To create a repository. Create or go to the directory that you want to create
the git repository in. Type `git init` to create an empty repository.

### Add a file & make a commit
You can type `git status` to see what files are in not in your repository, and
any files that you have changed. You can add those files by typing
`git add filename`. If you want to add all of the changed files you can type
`git add .` to add all of the changed files in your current directory (and it's)
children.

After you have added files, you can see the files you have added by typing
`git status` again. Once you've confirmed that you added all the files you want,
you can type `git commit` to commit those changes to the repository. You can
type in a commit message either in the text editor it opens or by typing
`git commit -m "A message"` for shorter messages.

Congrats! You've now committed your first files to git.

### View Changes
If you now type `git log` you will see your list of commits and commit messages.
There are a couple of things to note here. Every commit has a unique id, called
a hash. This is how git identifies all the commits. Since git keeps a record of
your files exactly how they were at every commit, if you ever want to go back
and look at how the code was at a specific commit you can use the command
`git checkout bc7cf239`. In this example `bc7cf239` is the hash of the commit.
To be a bit more specific it's actually only the first part of the hash, but git
is smart enough to identify which commit you're referring to even if you only
give it the first few characters.

To get back to your current state you can type `git checkout master`. The
`master` in that command refers to the branch that you're working on. In a
minute we'll see what branches are and how to use them.

## Github (Follow along here)
Git can be used by one person to track the status of a project over time, but it
becomes really amazing when you use it with other people. Github is a powerful
and free tool to let you collaborate with others. It lets you host a remote
git repository, and also offers some additional features such as forking and
issue tracking. I recommend following along with the rest of the tutorial
to familiarize yourself with git and Github, and how VC++ will be using both
tools.

### Fork a repository
Git allows you to host a remote repository on a server. This is basically like
a file server, but only for a single git repository. VC++ hosts all of our
repositories on Github. You're probably reading this on the web, so if you take
a look at the top part of the page you'll see all the files for the current
repository. If you own the repository you can browse and edit the files straight
from here, but you're probably going to want to edit the files on your computer.

To do this we first need to make sure you have permissions to commit to the
repository. With Github, you are able to commit to repositories you create,
repositories created by a team you're on, and repositories you are a
collaborator on. To make things simple, you are going to fork this repository
to your own account so that you own it and can commit to it without changing
anyone else's work.

Forking a repository simply means that you create a copy of the original on your
own account so you have permissions to edit it, and Github offers convenient
features to do this. Make sure you're logged into your Github account, then
click the fork button on the top right of this page (or whatever repository
you're trying to fork). Click on your account to fork it to your account, and
wait for it to copy the content. After a few seconds you'll see the same files
from the original repository, but it will be under your account and say "forked
from ..." underneath the name.

### Clone it to your computer
Great! Now you have your own copy of all the files you need. But how do you edit them? Github allows you to edit files on the website, but it is almost always easier to edit them on your local computer.

Cloning the repository simply means that you will create a copy of all the files and edit history on your computer so you can edit them. It automatically creates a reference to the server on Github so that you can *push* (pushing is basically uploading) your changes back to Github easily. You can clone any public  repository, but for this example we will clone the one we just forked.

Make sure you are on the right page (the repository name should say  your_username/Git-Tutorial) and find the button that says "Clone or download." Click on that and copy the URL from the box. Now go into your terminal or command line and navigate to a folder you'd like to keep the files in. Note that by default git will create a new folder in the current directory to keep the files in.

Once you've found a good location. Type `git clone  https://example.git.repo/myrepository.git` where the URL in the command is the URL you copied from the Github website. Hit enter and wait for your computer to download all of the files. After a few seconds type `ls` to see all of the files that are now downloaded.

It's important to note that you didn't just download the files. You also downloaded the whole history of the project. All of its previous commits and files are available for you to view and edit on your computer. For example, you can type `git log` to see all of the previous changes to the files.

### Make some changes
Now that we finally have the files on our computer, it's time to make some changes. Open up the `hello-world.html` file in a text editor. There are many different text editors available, but for this case any plain text editor (like TextEdit, Notepad, or GEdit) will work.

Once the file is open you'll see a very basic html document. If you know HTML feel free to change whatever you want. If you're not familiar with HTML open the document in a web browser. You might be able to double click on the file to open it, but if not open a web browser and click `File -> Open (File)` and navigate to the file.

You'll notice that there are 2 spots that say `[Your Name]`. One is in the title bar of the browser, the other is in the bolded text. To change this, go back to your text editor and look for those 2 spots in the code. Simply delete that text and fill in your name (or whatever you want).

Save the file and refresh the browser. You'll now see you're name on the webpage!

### Commit those changes
Now that we've made some changes, we are going to want to make a commit with a description of what we've changed. This is no different than earlier when we worked on the local git repository. Go back to your terminal and type `git status`. You'll see the `hello-world.html` file with `modified:` in front of it. You'll also notice that it says `Changes not staged for commit:` above the name of the file.

To add this file to the next commit type `git add hello-world.html`. Type `git status` again and you'll see that the file changed from `Changes not staged for commit` to `Changes to be committed`. Now we can make the commit. Type `git commit -m "Add my name to hello-world.html"`. This will create a new commit with a commit message "Add my name to hello-world.html".

Type `git log` and you'll see your new commit with your name and email at the top. Remember that this is still only on your local machine, so it won't be on your Github page yet.

### Push to a remote repository
But we should change that. Since we used the `git clone` command it's pretty simple to upload (or push) your changes back to Github. Type `git push` enter your Github login information, and it will upload your changes onto Github. If you go back to your Github page and hit refresh, next to the hello-world.html file you'll see your commit message, and if you click on the file you'll see your name in place of `[Your Name]`.
