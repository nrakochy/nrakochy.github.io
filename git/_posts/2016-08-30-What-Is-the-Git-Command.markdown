---
layout:     post
title:      What is the Git Command
date:       2016-08-30 12:00:00
summary:    What is the Git command for...
categories: command-line
---

What's the Git command for...? A quick reference to Git commands that I easily forget. Use (especially anything with `--hard` or `--force`) at your own risk!

Revert a specific file to a previous commit [source](http://stackoverflow.com/a/135614/3100284):

    #Get desired Head in the log (e.g. HEAD@{7})
    git reflog

    #Clip sha for easy pasting (e.g. HEAD@{7})
    git rev-parse HEAD@{7} | clip 
 
    #Checkout file to current working git 
    git checkout <PASTE> -- filename 

Undo a Git rebase [source](http://stackoverflow.com/a/135614/3100284):

    #Get desired Head@ in the log (e.g. HEAD@{7}
    git reflog

    #Save the existing, soon-to-be-deleted commit
    git tag RESET

    #Do it
    git reset --hard HEAD@{7}

    #Delete tag if everything went right
    git tag -d RESET

Replicating remote git locally [source](http://stackoverflow.com/a/1628334):

    git fetch origin
    git reset --hard origin/master

Synchronizing current branch with main branch (in this case develop branch), rewinding new changes to be on top of main branch

    git pull --rebase origin develop

Cherry-picking a range of commits (inclusive, oldest commit first) [source](http://stackoverflow.com/a/3933416):

    git cherry-pick 0123ab9^..456cd0

    #Get just one for your current branch
    git cherry-pick 0123ab9

View commit log by author across all branches after a given day (like today) [source](http://stackoverflow.com/a/4262780):

    git log --after="2015-11-11 00:00" --all --author="username" --pretty=format:"%h%x09%an%x09%ad%x09%s"

Fix the commit message [source](http://stackoverflow.com/a/179147/3100284):

    git commit --amend -m "New message here"
