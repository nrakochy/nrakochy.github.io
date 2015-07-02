---
layout:     post
title:      Build a Dockerfile With Boot2Docker on Windows 
date:       2015-07-03 12:00:00
summary:    How can I build a local Dockerfile from SSH session in Boot2Docker? 
categories: Boot2Docker 
---

How can I build a local Dockerfile from an SSH session in Boot2Docker on WindowsOS?

As of the writing of this post, Docker only runs on a Linux instance and cannot be fired up on Windows or Mac. 

[Boot2Docker](https://github.com/boot2docker/boot2docker) is a distribution which runs a small Linux container (with VirtualBox by default) and allows the Mac or Windows user to run Docker on their machine without too much pain.

However, in order to use the `docker` commands, you need to create an SSH session. (`boot2docker ssh`)

This gives you access to the Docker container world within a VM, not your local machine. So how can you access your local files to build a Dockerfile? 

The simplest way for what I needed was to use VirtualBox's sharing system, which is integrated with Boot2Docker.

So, open up VirtualBox - Settings - Shared Folders to see the path where the local machine's folders have been mounted.

Once you have the path, you can change into it, which will then allow you to build your docker file. For me: 

    cd  c/Users/nrakochy/Desktop/docker_test_run

    #double check that the Dockerfile is in the directory
    cat Dockerfile
    
    docker build -t my-new-image-name .


