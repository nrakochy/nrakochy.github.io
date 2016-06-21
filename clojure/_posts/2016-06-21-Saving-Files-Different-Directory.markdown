---
layout:     post
title:      Saving Files in a Different Directory   
date:       2016-06-22 13:00:00
summary:    Saving (platform-independent) files to a different directory in the filesystem 
categories: io 
---
Saving (platform-independent) files to a different directory in the filesystem with Clojure turned out to be a bit more difficult to track down than I expected, though the solution is simple enough. 

For a platform-independent approach, you can find the canonical path from a path relative to the project and then join it with the filename.

    (:require [clojure.java.io :as io :refer [file]])

    (defn file-dir 
      "Returns canonical path of a given path"
      [path] 
      (.getCanonicalPath (io/file path))) 

    (-> "./resources" ;; relative
      (file-dir)
      (io/file "filename.txt")) ;;=> /path/to/project/resources/filename.txt

 




