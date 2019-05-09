---
layout: post
title: "Wirth, Oberon and Simplicity"
cover: cover.jpg
description: ""
comments: true
categories: [simplicity]
date: 2013-04-25
---
Today I read a very interesting bit of computing science history, about Niklaus Wirth and the Oberon language/system: ['Oberon - The Overlooked Jewel'](https://www.ics.uci.edu/~franz/Site/pubs-pdf/BC03.pdf).

I've never written any Pascal - back in my school days, we were writing [COMAL](http://en.wikipedia.org/wiki/COMAL) on the BBC Micro (for some strange reason), when other kids would have been using Pascal.  I'd heard of it of course, believing it to be a more structured Basic.  I'd heard of Niklaus Wirth as the creator of Pascal, and I'd heard of Modula and Oberon, but I really didn't know much more than that.

It's quite understandable then, that the paper begins by describing with regret how Wirth is known as the creator of Pascal and as a 'language and compiler guy' to the detriment of his other claims to fame.

The description of the Oberon system is fascinating, but what interested me in particular was the discussion of Wirth's determined efforts towards simplicity.  The comparison of Wirth's Modula-2 and Oberon compilers against more complex compilers reminds me of [Go](http://golang.org/) with its incredibly fast compile times versus your typical modern day C++ compiler.

The use of self-compilation speed as a benchmark seems like a great way to target and then maintain a balance between complexity and the performance benefits of optimizations in a compiler.  Complex optimizations where the cost of optimization in terms of code complexity, outweigh the benefits of faster binaries could be clearly recognised with such a metric.  Perhaps there are more creative benchmarks we can use in other applications?

Another example of the struggle for simplicity is the description of Wirth removing a working high performance, elegant, but complex data structure from the compiler and replacing it with a linear list, despite the effort that had been spent on the more complex solution.  This data structure should have performed better, but the cost of its complexity was too high and the actual use case didn't play to its strengths.  The simpler solution turned out to be both smaller and faster in general use.

I'm a big believer in the benefits of simplicity over complexity in most cases, but it's rather hard to express it other than as instinct or experience.  The use of the self-compilation speed benchmark was able to highlight the cases where the complexity outweighed the benefit in a compiler, but at the moment I'm not sure of a good way to highlight these cases in a more general application.  There's still plenty of room for instinct and experience!
