---
layout: post
title: "Print Classpath in Clojure"
cover: cover.jpg
description: ""
comments: true
categories: [clojure]
date: 2013-07-06
---
Print out the current classpath, line by line, in Clojure:

{% highlight clojure linenos %}

(doseq [line (.getURLs (java.lang.ClassLoader/getSystemClassLoader))] (prn line))

{% endhighlight %}
