---
layout:     post
title:      Linux Permission Manipulation
date:       2015-06-30 12:00:00
summary:    Need a quick reference guide to linux commands for manipulating permissions?
categories: Linux
---

Need a quick reference guide to linux commands for manipulating file and directory permissions?

##Common Commands
To find the owner(s) of a directory:

    ls -l | awk '{print $3, $4 }' | sort | uniq

To change the permissions:

    chmod 600 filename

To change permissions by user type (use ‘+’ or ‘-’):

    chmod a+w filename

To change ownership (only from superuser):

    chown user_to_assign filename

To change group assignment:

    chgrp groupname filename

##Common settings
Permission definitions:

    Files:  r- read                              w- write           x- execute
    Dir:    r- directory can be listed if x      w- writable if x   x- directory can be entered

Settings:

    600 (rw-------): only owner can read/write
    644 (rw-r--r--): owner- can read/write; others- read only
    666 (rw-rw-rw-): all users can read/write
    700 (rxw------): owner- can read/write/execute; no one else can do anything with it
    755 (rwxr-xr-x): owner- can read/write/execute; everyone else- read/execute
    777 (rwxrwxrwx): all users have all permissions

(Note: Numbers starting with ‘7’ enable execution and are used for program files.)

##Users

    u =>    you
    g =>    group
    o =>    others
    a =>    all (all of the above- ugo)
    su =>   superuser (switches to root user)
    sudo => superuser (runs single command with root privileges)

[Source](http://linuxcommand.org/lc3_lts0090.php)

