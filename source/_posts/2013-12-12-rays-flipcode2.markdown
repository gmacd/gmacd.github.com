---
layout: post
title: "Rays - Now with Shadows, Reflection and Specular Higlights!"
date: 2013-12-12 07:02
comments: true
categories: [go, raytracing]
---
The second part in [Jacco Bikker's ray tracing tutorial on flipcode](http://www.flipcode.com/archives/Raytracing_Topics_Techniques-Part_2_Phong_Mirrors_and_Shadows.shtml) is over 9 years old, but that didn't stop me using it as a reference (ok, basically porting it).

The foundations were set in the previous article, and my implementation in Go was described here, and although the amount of code required to implement the features mentions in the second article, the difference in image quality is huge.  One of the nice things about ray tracing is that once you have the (relatively small) scaffold build to support shooting rays about a scene, adding features such as shading, reflection and specular highlights are straightforward and incredibly concise.

Here's the matching screenshot from my raytracer, suspicously identical to that in the flipcode article...

![Balls with Shadows, Reflections and Specular Highlights](/images/2013-12-12-flipcode2.png)
