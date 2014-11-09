---
layout: post
title: "ChanChan: File watching + web serving"
cover: cover.jpg
description: ""
comments: true
categories: [clojure, chanchan]
date: 2013-07-11
---
I've just comitted a new version of [ChanChan (0.2)](https://github.com/gmacd/chanchan/releases/tag/0.2) to github.  This relase is pretty small in terms of code changes, but adds some useful functionality:

* **Webserver**: ChanChan now uses ring to setup a webserver to serve the blog on port 3000.  There's currently no fallback if this port is unavailable.  To start the server, use `lein run`.
* **File watching**: ChanChan will watch the posts folder for any new or modified posts and convert them automatically.
