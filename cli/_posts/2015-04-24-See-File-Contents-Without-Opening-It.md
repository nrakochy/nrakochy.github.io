---
layout:     post
title:      See File Contents Without Opening It
date:       2015-04-25 12:00:00
summary:    How can you see what is inside a file without opening it from the command line?
categories: unix-commands
---

How can you see what is inside a file without opening it from the command line? Unix has
amazing powers. Use the `cat` (short for concatenate) command:

    cat filename1

This will give you look inside the file from the comfort of your CLI. Works with multiple files, too:

    cat filename1 filename2

You can even get line numbers if you would like:

    cat filename1 -n

