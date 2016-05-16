---
layout:     post
title:      Find first hash with matching key/value from sequence 
date:       2016-05-16 13:00:00
summary:    Find first matching record in Clojure sequence of hashes with unique value in a given key.
categories: cheatsheet 
---
Given a sequence of maps with common keys that have unique values, one need only to find the first matching. In this case, I needed to match a given URL to a defined URL with a path key: 

    (defn extract-matching-route [request routes-map]
      (let [requested-route (:uri request)]
      (some #(if (-> % :path (= requested-route)) %) routes-map))
    )

Found this little gem on SO, but can't seem to locate the answer, though there are several similar.
