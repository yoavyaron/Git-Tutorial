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
from here, but you're probably going to want to edit the files on your computer

### Clone it to your computer

### Make some changes

### Push to a remote repository
