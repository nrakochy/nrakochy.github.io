---
layout:     post
title:      What's the difference between Bytes and Bits in computer-speak? 
date:       2015-06-30 12:00:00
summary:    Bits- Data in motion. Bytes- Data at rest.
categories: miscellanea
---


Bits:
Data in motion

Bytes: 
Data at rest

There are 8 bits in 1 byte
If you assume that they are the same thing, you are off by 8x

Suppose you have a 80Mbps (megabits per second) download connection from Comcast.
In order to calculate time to transfer, how long a 20MB document will take to download, for example, you have to do a little bit of math.

Advertised Bit Speed: 80Mbps
Byte Speed: 10MB/second

Time to download: 2 seconds

Since you have 8 bits per second, you need to divide Bit Speed by 8: 

    80Mbps/8

which yields 10MB/second
