---
layout: post
title: "Subscribing to Document Key Events in Elm"
date: 2016-05-23 21:13
cover: cover.jpg
comments: true
categories: [elm]
---
How can do you respond to keyboard events in Elm?

Well, you could create an HTML element in your view, and add an event handler from [Html.Events](http://package.elm-lang.org/packages/elm-lang/html/1.0.0/Html-Events).  This would be the most idiomatic way if you want to capture these events from that particular element.

But what if you want to listen to events at the document level?  As it happens, this is my requirement, since I'm writing a full-page webapp.

The source for my current solution [can be found here](https://github.com/gmacd/elm-kbd-test).  At the time of writing, the current version attaches the keydown/keypress/keyup events to the document in the HTML wrapper, then sends messages down ports, which the Elm app has subscribed to.  This is then fed into the update handler.

It's not pure Elm, but it does the job!
