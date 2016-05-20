---
layout:     post
title:      Debugging a Clojure Exception in the Lien REPL 
date:       2016-05-20 13:00:00
summary:    Tips for debugging an exception in the Leiningen REPL. 
categories: cheatsheet 
---
See the exception stacktrace in the Leiningen REPL. When an exception is thrown in the REPL, it is saved to the variable `*e`. To see it, you can use the native Java command to print the stacktrace- 

    (.printStackTrace *e)

Picked this up from p.63 of [Joy of Clojure](http://www.joyofclojure.com/). After a bit more research (Googling, that is), Clojure has a couple other methods that help debugging. 

First, you need to require the stacktrace namespace (see here for the [right way](https://github.com/bbatsov/clojure-style-guide#prefer-require-over-use) to require namespaces): 

    (use 'clojure.stacktrace)

To see the root-cause, you can observe that in a nice map which gives `:cause`, `:via`, and `:trace`:

    (root-cause *e)

For a full stacktrace, use the Clojure print method which defaults to unlimimted lines shown (pass # of lines as 2nd argument to limit): 
    
    (print-stack-trace *e)

The shortest debugging method (which is an alias of the two methods above `(print-stack-trace (root-cause *e) 8))`) gives you the exception plus 8 lines:

    (e)

You can see the source code [here](https://github.com/clojure/clojure/blob/master/src/clj/clojure/stacktrace.clj)

