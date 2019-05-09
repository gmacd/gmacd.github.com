---
layout: post
title: "Essential Visual Studio 2015 Extensions"
cover: cover.jpg
description: "Essential Visual Studio 2015 Extensions/Plugins"
comments: true
categories: [vs2015, resharper]
date: 2015-08-19
---
[Visual Studio 2015](https://www.visualstudio.com/en-us/products/vs-2015-product-editions.aspx) has been out for 2 months now, giving enough time for popular extensions (and plugins) to be updated to support the new release, and also for some useful new extensions to be released.

The most popular plugin I've seen is the near-ubiquitous [Resharper](https://www.jetbrains.com/resharper/).  Resharper is extensive and powerful, with many more features than I've made use of.  Unfortunately these come at a cost.  I'm not just talking of the purchase and inevitable upgrade costs, but also the performance penalty paid by using Resharper.

For many people, a bit more sluggishness in Visual Studio is a price worth paying for all the features of Resharper, but in this day and age, I'd rather my IDE to be a bit more responsive.

With that in mind, I've not installed Resharper for VS2015.  Instead, I'm relying on the improvements in this latest version of the IDE, and on a small set of extensions:

* [NCrunch](http://www.ncrunch.net/) ($159) Okay, so I'll admit this one is commercial.  And it can be a bit of a performance hog (hopefully without slowing down VS too much though), but it's pretty essential.  If you haven't heard of it, it's a test runner extension that automatically runs your tests as you type (before you've even saved), giving you near-immediate feedback on the impact your changes have on your tests.  It also gives you inline code coverage information and generally makes it very easy to see what's tested, what's broken, and allows you navigate around and debug your tests.

* [Editor Guidelines](https://visualstudiogallery.msdn.microsoft.com/da227a0b-0e31-4a11-8f6b-3a149cf2e459) (Free) Extension allowing you to place column guidelines in the text editor.  Allows you to quickly see when you need to chide someone for going over 80 characters :)

* [Go To Implementation](https://visualstudiogallery.msdn.microsoft.com/0ed93222-83cd-4db3-92bc-a78909047156) (Free)  This is my newest discovery - a simple extension enabling you to go to the implementation of any symbol.  So far, this seems like a good replacement for one of the most useful Resharper features.

* **&lt;Any SCM plugin of your choice&gt;** Unfortunately, I need to use TFS....

Once you've installed those, you can probably go through all the pre-installed extensions, removing those you have no need for.

Congratulations, you now have a slimmed down modern IDE!

Any I've missed?
