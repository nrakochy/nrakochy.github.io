---
layout:     post
title:      Clojure Promotion with Numbers
date:       2016-05-31 13:00:00
summary:    Automatic detection and type conversion of large numbers in Clojure
categories: promotion 
---
Clojure detects when a number outgrows its class capacity and automatically converts the type to accomodate the bigger number a.k.a `promotion`:

    (def sample 10)
    
    (class sample) ;=> java.lang.Long
    (class (+ sample 1000000000000000000)) ;=> java.lang.Long
    (class (+ sample 100000000000000000000)) ;=> java.lang.BigInt
    (class (+ sample 1.0)) ;=> java.lang.Double

Source: [Joy of Clojure 69](http://www.joyofclojure.com/). 


