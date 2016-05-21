---
layout: post
title: "(Less) Recently Hard-Earned Wisdom"
date: 2016-05-20 13:39
cover: cover.jpg
comments: true
categories: 
---
I found this post today, written in April 2015, but never posted.  It was written after a period of frustration with the system and environment I was working with.  (I should probably try to summarize all I learned over the 2 years at that project sometime soon - this covers the first 9 months or so.)

So here they are, little pearls of unedited wisdom:
* The real reason for doing something in a certain way isn't always for the best of the team or product.
* When you get to the point where smart people don't understand fundamental parts of the code because of complexity, you have a problem.
* When you have too many layers of abstraction, you add to the problems.
* New layers of abstraction are all too easily added.
* If there is no ownership of an area, more changes are done while only thinking of the short-term.
* People dedicated to maintaining one particular piece of infratructure aren't always as proactive as you'd like.
* Dependencies on other teams within the same organisation should be avoided.
** Other teams may have other priorities.
** Other teams may not be very efficient.
** Perhaps a brokerless message queue is a better idea than one where the queues are controlled by a single seperate group, if it otherwise meets the requirements.
** Maybe it's better for the team to take ownership of the databases.
** Maybe this leads to the infrastructure the team depends on being simplified out of the necessity of support.
* Once the amount of legacy reaches a critical mass, it's very difficult to get rid of.
* Running out of RAM on a DB server manifests itself in disk thrashing and general slowness of queries.
* Complexity should be avoided wherever possible.  Clever solutions can come with a cost.
