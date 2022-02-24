# Git Reference

## Definitions
Commit - an object.\
Branch - a reference to a commit; can have a tracked upstream.\
Tag - a reference (standard) or an object (annotated)\
Head - a place where your working directory is now.


## Installation Notes
Note: Some GNU/Linux distributions do not have the newest version of Git. To install the most up-to-date version for Debian/Ubuntu:\
`git --version` - check version of Git (not required).\
`sudo add-apt-repository ppa:git-core/ppa` - add a PPA (Personal Package Archive) maintained by the Git team for Debian/Ubuntu.\
`sudo apt update` - update repository cache.\
`sudo apt install git` - install Git from new source.

## Basic Flow
`git clone [url/project.git]` - retrieve an entire repository from a hosted location via URL.\
`git add .` - add all files (that are not listed in the .gitignore) in the entire repository to the staging area.\
`git commit -m "[Comment]"` - create an initial commit from files added to the staging area. comment conventions: capitalize the subject line. do not end with a period. use the imperative mood. e.g., "Update getting started documentation", "Remove deprecated methods".\
`git push origin main` - push local branch to remote repository. "origin" is the remote for [url/project.git] and "main" is the branch.\
`git status` - displays the state of the working directory and the staging area.


## Typical Setup

### Git global setup
`git config --global user.name "[firstname lastname]"` - set the name that will be attached to your commits and tags.\
`git config --global user.email "[valid-email@domain.tld]"` - set the email address that will be attached to your commits and tags.

### Create a new repository
`git clone [url/project.git]` - retrieve an entire repository from a hosted location via URL.\
`cd [project]` - cd to project directory on your machine.\
`git switch -c main` - create branch main and switch to it. `-c` is create option./
`touch README.md` - create README.md file.\
`git add README.md` - add README.md to the next commit (staging area).\
`git commit -m "Add README"` - create a new commit from changes added to the staging area. `-m` is message option.\
`git push -u origin main` - push local branch to remote repository. set its copy as an upstream. `-u` sets copy as upstream.

### Push an existing folder
`cd existing_folder` - cd to an existing folder on your machine. \
`git init --initial-branch=main` - initialize an existing directory as a Git repository with a branch named "main".\
`git remote add origin [url/project.git]` - add a remote named origin for the repository at [url/project.git]. after adding a remote, you'll be able to use "origin" as a convenient shortcut for [url/project.git] in other Git commands.\
`git add .` - add all files (that are not listed in the .gitignore) in the entire repository to the staging area.\
`git commit -m "Initial commit"` - create an initial commit from files added to the staging area.\
`git push -u origin main` - push local branch to remote repository. set its copy as an upstream. `-u` sets copy as upstream.

### Push an existing Git repository
`cd existing_repo` - cd to an existing repo directory on your machine.\
`git remote rename origin old-origin` - rename remote origin to old-origin.\
`git remote add origin [url/project.git]` - add a remote named origin for the repository at [url/project.git]. after adding a remote, you'll be able to use "origin" as a convenient shortcut for [url/project.git] in other Git commands.\
`git push -u origin --all` - push all branches.\
`git push -u origin --tags` - push all tags.


## Other
`git config --list` - show git config settings, such as user.name and user.email.\
`git rm --cached [filename]` - remove [filename] from staging area.\
`git branch` - list all of the branches in your repository. this is synonymous with `git branch --list`. use `-a` to list local and remote branches.\
`git branch [branch-name]` - create a new branch called [branch-name]. this does not check out the new branch.\
`git checkout [branch-name]` - point HEAD to the tip of [branch-name].\
`git checkout -b [branch-name]` - shorthand for `git branch [branch-name]` and `git checkout [branch-name]`. creates and checks out [branch-name]. the `-b` option is a convenience flag that tells Git to run git branch before running git checkout [branch-name].\
`git pull origin [branch-name]` - pull an existing branch [branch-name].