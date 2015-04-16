---
layout:     post
title:      Debugging with Git in the Browser
date:       2015-04-16 12:00:00
summary:    How can I use git for debugging in the browser?
categories: debugging
---

How can I use my `git commits` for debugging in the browser?

On a recent feature in the not-too-distant-past, my Bootstrap js dropdown navigation menu in Rails
inexplicably stopped working.

Assuming this was a mistake that I added to the branch, I switched to the master and restarted
the Rails server. Still not working.

At this point, I obviously need to see at what point I broke this and I had no idea what changed.
It was working earlier in the day, but that was my last point of reference. Enter `git`

Git allows you to checkout a previous commit as a branch to work from. In order to see your git history, you 
need the git log:
    git log

This will give you a list of commits:
    commit 123456abcdefghijklmnop123456lmnopq123456
    Author: user <user@example.com>
    Date:   Tue Apr 14 13:42:40 2015 -0500

        Added Procfile

    commit 123456abcdefghijklmnop123456lmnopq987654
    Author: user <user@example.com>
    Date:   Tue Apr 14 13:39:55 2015 -0500

        Changed to Puma server

In order to switch to a branch with the commit, you need to checkout the branch
    git checkout -b 123456abcdefghijklmnop123456lmnopq987654

Note: if you have already done this, then the branch exists already. In that case get rid of the -b
to switch the branch:

    git checkout 123456abcdefghijklmnop123456lmnopq987654

This process was helpful to see where I introduced the bug, but not so much to fix it i.e. you
probably do not want to merge from this git branch that you just created.

Once you are on the branch, you can fire up ye olde rails server:
    rails s

Open your browser on the your localhost, and check the feature to see if it is working.
If not, repeated process above. If so, you are on the right path to find the error. Happy bug hunting.














