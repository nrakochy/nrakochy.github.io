---
layout:     post
title:      No Submodule Found In .gitmodule
date:       2015-05-21 12:00:00
summary:    What is a git submodule and where did it come from?
categories: Submodule
---
What is a git submodule and where did it come from?

I recently worked on a project that had multiple independent programs that I needed to write.

These were committed to a git repo.

One of the programs was an API library, for which I decided to create a separate repo with a different name,
as it had other use cases for me.

When I pushed the umbrella project to Github, lo and behold, I see this:

    -Subproject commit 1515a6f60156cb658036ba6008759fd9509fc17f

That is, I only see this commit id, and there's no code. From multiple files to this awesome
one-liner.

This is by design in Git, so that you can ["clone another repository into your project and keep your commits separate](https://git-scm.com/book/en/v2/Git-Tools-Submodules).

A submodule is effectively a reference to a separate Git project via a particular commit. (I didn't find a clear definition in the [docs](http://git-scm.com/docs/git-submodule))

However, for my project, I needed the code not a commit number! Where is it?

It is still in the other git repo, completely separate.

Per the [docs](http://git-scm.com/docs/git-submodule) and StackOverflow, I tried this to fix it:

    git submodule update --init

To no avail. This gave me the error:

    No submodule mapping found in .gitmodules

I do not know why the submodule reference would not be in the .gitmodules. Whatever the reason, this did not work.

What I needed to do is delete the cache (which I also found on StackOverflow [here](http://stackoverflow.com/a/13394710)):

    git rm --cached path/to/gitrepo

(By the way, I don't actually use `rm`, but have disabled it and use an alias to move files and directories into the Trash.
Use at your own risk.)

Now you should be able to `git add .` and `git commit`, and the code from the submodule should be included in the umbrella project’s git repo.
Once you push to Github, all the code should be in place.









