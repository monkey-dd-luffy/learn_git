# Installation
```
sudo apt-get install git
```
# First-Time Git Setup
```
git config --global user.name "Your Name"
git config --global user.email your.email@example.com
git config --global core.editor YourEditor
git config --list
git config <key>
```
# Getting Help
```
git help <verb>
man git-<verb>
```
# Common commands
```
git init
git add filename
git add *.ext
git commit -m "commit message"
git clone <url>
git clone <url> <directory name>
git status
git status -s
git diff
git diff --staged
git rm filename
git mv file_from file_to
git log
```
# Ignore Files
```
cat .gitignore
*.[oa]
*~
```
* blank lines or lines starting with # are ignored
* standard glob patterns work, and will be applied recursively throughout the entire working tree
* start patterns with / to avoid recursively
* end patterns with / to specify a directory
* negate a pattern by starting with !

# Working with Remotes
```
git clone <url>
git remote [-v]
git remote add <shortname> <url>
git fetch <remote>
git push origin master
git remote show origin
git remote rename old_name new_name
git remote remove remote_name
```
# Tagging

## Listing Your Tags
```
git tag
git tag -l "v1.8.5*"
```

## Creating Tags
```
git tag -a v1.4 -m "my version 1.4"
git tag show v1.4
```

## Sharing Tags
```
git push origin v1.5
git push origin --tags
```
## Checking out tags
```
git checkout tag_name
```

# Git Aliases
```
git config --global alias.co checkout
git checkout == git co
```

# Git Branching

## Creating a New Branch
```
git branch branch-name
```

## Switching Branches
```
git checkout branch-name
```
## Example: Basic Branching and Merging
working on the master branch and decide to work on issue #53
```
git checkout -b iss53
do some work
git commit -a -m 'added a new footer [issue 53]'
git checkout master
get a hotfix
git checkout -b hotfix
do some work
git commit -a -m 'fixed the broken email address'
git checkout master
git merge hotfix
git branch -d hotfix
git checkout iss53
do some work
git commit -a -m 'finished the new footer [issue 53]'
git checkout master
git merge iss53
git branch -d iss53
```

## Basic Merge Conflicts
```
git branch --merged
git branch --no-merged
git branch --no-merged master
```

## Branching Workflows
### Long-Running Branches
* master branch: the stable/release version
* develop/next branch: the unstable version, will merge to master after testing
### Topic Branches
short-lived branch that you create and use for a single particular feature or related work. deleted after merging with master

### Remote Branches
* list full list of remote references
```
git ls-remote [remote]
git remote show [remote]
```
Remote branches take the form <remote>/<branch>, e.g. origin/master

* clone remote
``` 
git clone
```
automatically create remote origin and local branch master, which is different from origin/master

* synchronize with remote
```
git fetch origin
```
get new data and move origin/master to its new position

* pushing
```
git push <remote> <branch>
git push <remote> <local branch name>:<remote branch name>
```
when you fetch a remote and get a new branch, it is not locally branch, only a pointer to the remote branch. you need to
* merge it into your working branch
```
git merge origin/newbranch
```
* create your own local branch based off this remote branch
```
git checkout -b localbranch origin/newbranch
```

#### tracking branches
```
git checkout --track origin/serverfix
git checkout -b localbranch origin/serverbranch
```
creates a tracking branch. so then you do git pull, Git automatically knows which server to fetch from and branch to merge into

when you clone a remote, master tracks remote/master
```
git branch -u origin/serverfix
```
use a existing local branch to track remote branch

* reference a tracking/upstream branch
```
@{u}
git merge @{u}
```
* show upstream branches
```
git branch -vv
git fetch --all; git branch -vv
```
#### pulling
```
git pull
```
pull down changes on the server and commit. It is recommended to use git fetch + git merge instead

#### deleting remote branches
```
git push origin --delete branchname
```

#### Rebasing
```
git rebase branch-to-base-on
git rebase <basebranch> <topicbranch>
```

* do not rebase commits that exist outside your repository

# GitHub
## SSH Access

## Workflow
* Fork the project
* Create a topic branch from master
* Make some commits to improve the project
* Push this branch to your GitHub project
* Open a Pull Request on GitHub
* Discuss, and optionally continue committing
* The project owner merges or closes the Pull Request








