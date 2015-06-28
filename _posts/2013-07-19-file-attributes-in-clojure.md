---
layout: post
title: "File attributes in Clojure"
cover: cover.jpg
description: ""
comments: true
categories: [clojure, chanchan]
date: 2013-07-19
---
While writing [ChanChan](https://github.com/gmacd/chanchan) I wanted to get the creation time of a file.  `java.io.File` only gives you the last modified time, which isn't quite what I was after.  Java 7 has `BasicFileAttributes`, from which you can access the creation time, last modified time, size, etc.  To get an instance of this interface, you need to call `Files.readAttributes`.  This turned out to be quite fiddly in Clojure (at least for me, a relative newcomer!), so I'm putting to here in case anyone else is looking for it.  (Hopefully the namespace is correct - it's been edited from my original code...).

{% highlight clojure linenos %}

(ns foo
  (:require [clojure.java.io :as jio])
  (:import (java.nio.file Files LinkOption)
           (java.nio.file.attribute BasicFileAttributes)))

(defn file-attributes [file]
  "Return the file BasicFileAttributes of file.  File can be a file or a string
   (or anything else acceptable to jio/file)"
  (Files/readAttributes (.toPath (jio/file file))
                        BasicFileAttributes
                        (into-array LinkOption [])))

{% endhighlight %}