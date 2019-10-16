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

# Git Aliases
```
git config --global alias.co checkout
git checkout == git co
```

# Git Branching
