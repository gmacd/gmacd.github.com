---
layout: post
title: "TODO: Wiki"
description: ""
comments: true
categories: [todo, wiki]
date: 2013-05-18
---
One of my preferred ways of procrastinating is thinking about organising todo lists (the programmer in me wrote 'TODO' there and had to go back and change it - disappointed it's not syntax highlighted here...).  I'd like to combine todo lists with more general notes, documents, my calendar, etc., and have it all versioned too.  Oh, and it should be cross platform and the data should be accessible and up to date from home, work or anywhere else.  And it should be secure.  I'd like to be able to do some spreadsheet-like data manipulation and graphing too.

Now if I want to do all that, I'll have to write something myself.  I could probably use something like [Evernote](http://evernote.com/) to get part way there, but I don't want to pay for a service I'd then feel locked into, and anyway it's not quite what I have in mind.

Ideally, I'd like to be able to do all this without having to install anything on the client, so this basically means a website.  Or a text file.  Or maybe some heavy customization of [Emacs org-mode](http://orgmode.org/)?  (That's assuming Emacs is already installed, so not really cheating...)

One possibility, which doesn't meet all the requirements, but is interesting all the same, is [TiddlyWiki](http://tiddlywiki.com/).  I've tried TiddlyWiki before, using it while trying to [Get Things Done](http://en.wikipedia.org/wiki/Getting_Things_Done).  The idea is that you have a single html page, no server, providing a wiki, and any modifications get saved out to the same html page.  There's no versioning, but rather than operating at the level of wiki 'pages', you create notes instead.  You can have several open for viewing or editing at once.

It all works pretty well, at least in Firefox with the [TiddlyFox](https://addons.mozilla.org/en-US/firefox/addon/tiddlyfox/) extension to enable TiddlyWiki to save itself.  I had issues using Chrome on my Mac, so stuck to Firefox.

For whatever reason, I didn't use it for very long, but recently I noticed that a rewrite is in progress, so took another look.  [TiddyWiki5](http://five.tiddlywiki.com/) can be used without a server as before, or served by node.js.  It's alpha, and I've just started using it, so it's way too early to comment much on it, but it looks promising.  Using it as a standalone HTML file on Chrome still seems to have issues, and unfortunately Firefox still needs the TiddlyFox extension to work well.  You also need to remember to save before quitting.

Anyway, this post was a bit more rambling than I intended (even moreso now...), but this is an area that interests me, so hopefully I can write a bit more about how I get on with TiddlyWiki5, maybe a bit about Ward Cunningham's [Smallest Federated Wiki](https://github.com/WardCunningham/Smallest-Federated-Wiki) (I saw an excellent presentation by him about his new wiki at QCon London earlier in the year), and maybe even a little about my own work in this area, if it ever gets far enough along to talk about.
