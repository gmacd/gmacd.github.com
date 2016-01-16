---
layout: post
title: "Query GCC Optimization Flags"
date: 2016-01-03 09:15
cover: cover.jpg
comments: true
categories: [code]
---

In my last post, I showed a way of querying which machine-dependent flags were implied by a particular gcc invocation.  An example would be:

`gcc -Q --help=target -march=native`

Another possible query is to find which optimization flags would be set for a given gcc invocation.  This is particularly useful for finding out which flags are set for each optimization level.  E.g., to find which are set for O3:

`gcc -Q --help=optimizers -O3`
