---
title: "Dishes in the Sink"
date: 2018-03-03T07:08:51-07:00
draft: false
---

Have you ever witnessed a broken process that was obviously broken and doomed fail? Not because it couldn’t work. The process would never work simply because the owner of the process was blind to why it didn’t work: The human factor. I’ve seen this in security all too often. We often want to ignore how our brains work and [blame the training] (https://ericalexander.org/posts/security-awareness-training-what-works/) or blame human nature. Proposed fixes are often more training or threats of termination.

The question we should be asking when a process routinely fails: Is it a [human error or a designer error] (http://www.apa.org/monitor/feb06/closer.aspx)? I’m convinced most broken processes lack [feedback loops] (https://www.wired.com/2011/06/ff_feedbackloop/). I’m also a big believer in using automation to eliminate toil. 

The Problem
-----------

I’m a father of two teenagers. They’re great kids and they’re just that: Kids. They’re developing and learning. They were struggling with one thing, it seemed no matter how much I tried I couldn’t get them to consistently put their dishes in the dishwasher. It started to feel like an endless loop. I’d come home, there would be dishes in the sink, and a dish investigation would begin. 

Verbal feedback wasn’t working mostly, I think, due to a lack of immediate feedback. While not verified, I think the verbal feedback would have worked if I camped out by the sink 24/7 - who’s got time for that?

The Solution
------------

Feedback was working but it needed automation, it needed to be immediate feedback. The process needed a way to detect dishes in the sink and provide immediate feedback that they shouldn’t be there. That’s how the [DishDetector] (https://github.com/ericalexanderorg/DishDetector) came to be. 

The DishDetector is fairly simple. It’s a Rasberry PI, with a camera, and in its current iteration it also has a buzzer. It’s job is to take a picture of the sink, detect circles (likely dishes), and make an annoying buzzing sound if dishes are detected. 

The Results
-----------

This is a stick in the form of an annoying buzzer, it’s not a carrot. Motivating with a stick tends to lead into a cat and mouse game. I fully expected my kids to start gaming the detection. To my surprise, it worked and they haven’t tried to game it, yet. 

The results were so immediate and consistent that I started to suspect they no longer benefited from the invention, that was, until we went on vacation. I didn't want to annoy our house sitter while we recently went on vacation, so I disabled the device. I forgot to turn it back on when we came home, wouldn’t you know it, the dishes started piling up again. Turns out the kids still need a feedback loop. 

An Observation
--------------

The first iteration of the DishDetector used Slack as the feedback mechanism. Using Slack also had the benefit of easily recording transitions from no dishes in the sink to many, it served as an audit log. Turns out channel notifications are inconsistent on the mobile version of Slack, resulting in an inconsistent or broken feedback loop.  

It was during one of these transitions that I noticed something interesting. It only took one dish in the sink to provide social proof that it was OK for dishes to be there. Turns out that first dish was often put there by my wife. I’m not saying my wife was the root cause but I am saying it became evident she contributed. 

[Social proof] (https://blog.hubspot.com/marketing/social-proof-examples) is a powerful sociological motivation, a tool often used by marketers, a tool we should leverage in security to help guide people towards the right choice. Think about it the next time you run an in-house phishing campaign. Communicate and celebrate when people make the right choice. 