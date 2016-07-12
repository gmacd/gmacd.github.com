---
layout: post
title: "Git Submodules"
date: 2016-07-12 11:00
cover: cover.jpg
comments: true
categories: [git]
---
[From here](https://medium.com/@porteneuve/mastering-git-submodules-34c65e940407#.oxlw219r2), how to update submodules (amongst other submodule wisdom).

Update git submodule:

* In the submodule:
** `git fetch`
** `git log --oneline origin/master -10` Get the latest checksum
** `git checkout -q 79fa48a` Checkout the latest commit
** Commit and push
* In the parent repo:
** Push

Git config settings for better diff and log messages:

* `git config --global diff.submodule log`
* `git config --global status.submoduleSummary true`

Random useful command lines:

* `cd -` Bounce between current and previous paths
* `git log --oneline` Oneline git log
