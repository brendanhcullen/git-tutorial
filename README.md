# Git Tutorial

## Install git
1. Open the command line
2. To check to see if you have git installed
```
git --version
```

2. To install on a Mac, type (this will install a pared down version of XCode that includes git)
```
xcode-select --install
```

3. For other operating systems, following [these directions](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

## Create an account on GitHub and join UO Data Science organization
1. Go to [GitHub](https://github.com/) to create an account
2. Go to [UO Data Science](https://github.com/uodatascience)
3. Add username to list on Slack to be added to the organization
4. Accept email invitation

## Why version control?
* To have a backup
* To work collaboratively and avoid conflicted copies
* To avoid this:

![Avoid this](http://www.phdcomics.com/comics/archive/phd101212s.gif)

## Key concepts (Git 101)
* **Snapshots** = records what the files look like at a given point in time
  * You decide when to take snapshots
  * History of all snapshots is retained
* **Staging** = which files to include in the snapshot
  * You decide which files you want to take snapshots of
* **Commit** = the act of creating a snapshot
  * Info that's been changed
  * A reference to the commit that came brefore it (parent commit)
* **Repository** = collection of files and file history
	* Local repository = exists only on your local machine
	* Remote repository = exists on a remote website (e.g. github.com, gitlab.com, bitbucket.org)
* **Cloning** = copying a repository
* **Pulling** = grabbing changes from the original repository
* **Pushing** = pushing changes to the original repository
* **Branches** = offshoots of the master branch
  * Master = typically the main branch
* **Merging** = combining branch with master repository

## Basic process
1. If using a remote repository, pull recent changes
	* Get most up to date version of the repository
	* `git pull`
2. Make changes to a file
3. Stage the file 
	* Choose to take a snapshot of the changes 
	* `git add [file]`
4. Commit the changes
	* Take a snapshot of the file
	* `git commit -m "I made these changes.." [file]`
5. If using a remote repository, push changes
	* Apply your local changes to the repository
	* `git push`
6. Rinse, repeat.

## Tutorial
### Local use
1. Make directory on your desktop
```bash
mkdir ~/Desktop/git-test
cd ~/Desktop/git-test
```
2. Initialize the repository
```bash
git init
```
3. Check what's in the directory
```bash
ls -a
```
4. Get status
```bash
git status
```
5. Create file
```bash
printf "I <3 git" > test.txt
```
6. Check status
```bash
ls 
git status
```
7. Add test.txt file to the repository
```bash
git add test.txt 
```
8. Check status
```bash
git status
```
9. Save snapshot of repo by commiting changes
```bash
git commit -m "added test file"
```
10. Check version history
```bash
git log
```

### Remote use
1. Update global configurations
```bash
git config --global --list
git config --global user.name 'Dani Cosme'
git config --global user.email 'dani.cosme@gmail.com'
git config --global core.editor 'sublime'
```
2. Clone git-tutorial repo
```bash
cd ~/Desktop
git clone https://github.com/uodatascience/git-tutorial.git
```
3. Check status
```bash
git status
```
4. Get most up to date version of the repo
```bash
git pull
```
5. Open favs.txt file with text editor
```bash
# open in text editor app
open /Applications/TextEdit.app favs.txt
# open in terminal using vim
vim favs.txt
```
6. Add your favorite R package and save file
```bash
# add txt directly from command line
printf "\ndplyr" >> favs.txt
```
7. Add favs.txt to the staging area
```bash
git add favs.txt
```
8. Commit changes
```bash
git commit -m "added fav package"
```
9. Push changes to github repo
```bash
# single master branch
git push

# multiple branches
git push origin [branch name]
```
10. Pull newest version from the github repo
```bash
# single master branch
git pull

# multiple branches
git pull origin [branch name]
```

## Commonly used commands
```bash
# initialize repository
git init

# add file(s) 
git add [file]  # single file
git add .       # all files

# make a snapshot of repository
git commit -m "[message text]"

# copy existing repository
git clone [repo address]

# get newest version of repository
git pull

# push changes to repository
git push

# view history
git log

# check changes that have been made to files in a repository
git diff

# create new branch
git checkout -b [name of new branch]

# switch branches
git checkout

# check configurations
git config --global --list
```

## Resources
* [Git 101 – HubSpot](https://www.slideshare.net/HubSpot/git-101-git-and-github-for-beginners)
* [Git Intro – Ariel Rokem](http://arokem.github.io/2013-09-16-ISI/lessons/git-notebook/git-for-scientists.slides.html#/1)
* [Reproducible Workflows – Russ Poldrack](https://github.com/poldrack/reproducible-workflows)
* [Git Cheatsheet – Roger Dudler](https://rogerdudler.github.io/git-guide/files/git_cheat_sheet.pdf)
* [Git Cheatsheet – NDP Software](http://ndpsoftware.com/git-cheatsheet.html#loc=remote_repo;)
* [Git: the Simple Guide](http://rogerdudler.github.io/git-guide/)