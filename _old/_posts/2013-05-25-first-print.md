---
layout: post
title: "First Print"
cover: cover.jpg
description: ""
comments: true
categories: [3dprinter, makerbot, cupcake]
date: 2013-05-25
---
After much fiddling (and wailing, and gnashing of teeth, and crashing of build platform) I've managed to get the old Cupcake to complete its first print in about 3 years: a (shrunken) [door stop](http://www.thingiverse.com/thing:2154).  It's too small to be useful for our doors, but I'm quite happy with it as a first print.

It took a few hours of trial and error to get from the stage of being able to test the individual axes and the nozzle temperature to getting a complete print.  Most of the time was spent trying to find the appropriate version of [ReplicatorG](http://replicat.org/) and the motherboard firmware.

Of course my first try was with the latest and greatest ReplicatorG (040) and the latest version of the firmware that looked like it might work.  It didn't.  I could move the axes or change the temprature, but trying to build would hang ReplicatorG at the build estimation stage.  After a search, I found a suggestion of replacing all the E&lt;Num&gt; instances in the gcode with A&lt;Num&gt;, but this didn't work.

After a bit more fiddling, and still no success, I tried [Makerware](http://www.makerbot.com/makerware/), by Makerbot.  I've not being paying much attention to the 3D printer world, but it seems that Makerbot have pretty much abandoned the basic Cupcake.  Makerware doesn't support it, and they've also removed their wiki, which had all the build & setup instructions for their printers.  (You can [download it as an archive](http://www.makerbot.com/support/archive/), but that doesn't help when trying to search the web for anything in the wiki.)

I then went back in time, trying out increasingly older versions of ReplicatorG and the firmware.  I eventually settled on version 025 of ReplicatorG, and the oldest version of the firmware it provided, which eventually resulted in this:

![First Print: A (shrunken) door stop](/images/first_print.jpg)

I might try to upgrade everything again, until I find the latest version I can use, but I'm happy with this minimum for now.
