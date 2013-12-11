---
layout: post
title: "ChanChan: Posts listed on front page"
description: ""
comments: true
categories: [clojure, chanchan]
date: 2013-07-15
---
A bit more work has been done on ChanChan, enough to merit a new tag - [0.3](https://github.com/gmacd/chanchan/releases/tag/0.3)!

The fundamental change is that ChanChan now shows a list of links on the front page to all the posts.  In making this change, quite a few of the functions have been modified, making it a bit easier to reuse useful data at different points in the post conversion pipeline.

A couple of random thoughts occured to be while making these changes:
* Clojure functions tend to be small.
* I have to put a lot of thought into how best to write the code, or how best to change it.  I've never written a static web page generator before, but I imagine I could knock one up in C# (the main language I use at work) pretty quickly.  I'm not sure if I'm taking more time due to my relative lack of familiarity with the language, or if it's a more general side-effect of functional or lisp programming.
* .Net has much better facilities for operating on paths.  Or maybe Java/Clojure has better facilities that I'm not aware of...
* I'm pleased with the size of the codebase.  It's currently running at 107 lines of code, with comments, docstrings and empty lines (HTML templates excluded).  I'm not actively trying to minimize the number of lines used, but I'd like to get a minimal useful site generator fitting comfortably into a single Clojure file without it feeling forced or being detrimental to understanding the code.

Looking forward, the next step is to add some metadata to the posts and begin to extract it.  I'm thinking of post titles initially, and then perhaps tags.  Unfortunately, Markdown doesn't seem to support metadata by default, although there appear to be some extensions that support this.  Time for some googling...