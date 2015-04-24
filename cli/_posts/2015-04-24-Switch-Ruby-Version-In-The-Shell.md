---
layout:     post
title:      Switch Ruby Version In Your Terminal with rbenv
date:       2015-04-24 12:00:00
summary:    `rbenv shell 2.2.0`
categories: rbenv
---

How can you switch between Ruby versions in Terminal? Say you want to give `jruby` a test-drive.
Once it is bundled up, you use this command to switch for your current session:

    rbenv shell jruby-1.7.18


To verify that switch did indeed work:

    ruby -v


Which will give you the output:

    jruby 1.7.18 (1.9.3p551) 2014-12-22 625381c on Java HotSpot(TM) 64-Bit Server VM 1.8.0_25-b17 +jit [darwin-x86_64]


To switch to any Ruby version, you do not specify `Ruby` explicitly, but instead reference it by the version number:

    rbenv shell 2.2.0


