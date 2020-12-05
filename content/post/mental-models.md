---
title: "Mental Models"
date: 2020-12-05T11:50:35-07:00
draft: false
---

Is Youtube machine learning drawing a connection between Steve Jobs and DevOps? Is that why Youtube keeps recommending a Steve Jobs related video after I watch a DevOps related video?

Maybe Youtube is on to something. I had an aha moment after watching an interview with Andy Miller about the Apple acquisition of his company, Quattro Wireless. Andy talks about [Steve’s constant demands to simplify](https://youtu.be/k7f-51oy0OA?t=2047), and his advice to Andy: “[Use a picture. I don’t want to see a deck with a hundred words on it. I want you to think like an Apple guy](https://youtu.be/k7f-51oy0OA?t=2129)”. 

A light bulb went off when I heard that. It's the same problem Peter Drucker talks about in The Fifth Discipline: 

> Perhaps the single greatest liability of management teams is that they confront complex, dynamic realities with a language designed for simple, static problems 

I’m lucky to work at a company that’s both global, and decentralized. Our HQ is in Ventura California, but only a fraction of our company calls California home. We’re all over the world. I may start my day on a Zoom with somebody in London and may end it on a Zoom with somebody in Shanghai. In many ways our offices are perks, they’re not required; so when the pandemic hit, it was barely a speedbump. 

I don’t need to be in an office to get things done, but there’s one office tool that’s been hard to replace: The whiteboard. Sometimes it’s hard to figure out [who’s on first](https://youtu.be/kTcRRaXV-fg) over Slack or Zoom. Sometimes it’s easier to say “Let’s whiteboard this” and hours of potential conversation are distilled down to a diagram of who’s on first. Take a picture of that diagram and there’s exponential ROI as the output of the mind meld is shared with a global team.

![mind meld]("/mind-meld.png")

How do you boil complex topics down to an image, when there’s no whiteboard to share? I've tried to whiteboard over Zoom, just isn't the same. It's clunky and less interactive. What works? Let’s walk through a complex topic using some alternative tools, but let’s start by exploring the topic without them. Let’s say we’re on a Zoom with the CEO and the CISO of a company that’s cleaning up from a ransomware incident. The CEO is trying to figure out what’s needed to prevent another incident. 

Maybe the conversation goes like this:

CEO: How did ransomware get on our network?

CISO: Eric in HR opened a phishing attachment and it spread from there. 

CEO: Eric in HR is an idiot who can’t spot obvious phishing, fire him. Problem solved.

Problem solved, or an example of what Peter Drucker was describing? The CEO is confronting a complex problem with language designed for a simple problem? Does the CEO have an accurate mental model from that simple conversation? [Same mistake Pitney Bowes made](https://www.forbes.com/sites/leemathews/2020/05/12/ransomware-hits-pitney-bowes-for-second-time-in-less-than-a-year/?sh=14ae094c2d35)? 

What if the CEO explored past the first order problem of Eric falling for phishing? What if the CEO asked for a sequence diagram of events first?

![ransomware sequence diagram]("/ransomware-sequence-diagram.png")

The sequence diagram helps us see there’s a bigger problem beyond the first order problem of Eric falling for phishing. How can we understand:

* Who’s behind ransomware?
* Why are they doing it?
* How are they doing it?
* Who are they targeting?

When we start to explore and capture in a mind mapping tool we’ll end up with something like this that [we can share with the team to explore](https://coggle.it/diagram/X8u81lJoLC5D-gR6/t/-/de76c0a8c13ac723f6a788f4e4f05a9fe2d46a1da3d24b4f39eee93f20a658e4). 


That mapping helps us understand how it works. It gives us some insight into birds eye view cause and effect relationships, but doesn’t help us understand why we’re vulnerable - we need a Current Reality Tree.

![ransomware mind map]("/ransomware-mind-map.png")

[Check out this past blog post](https://ericalexander.org/post/devops-and-ransomware/) if you’d like to understand how the current reality tree was built and how to use it. 

What works better? Hours of back and forth over Slack or Zoom discussing a complex problem or an infographic that everyone can understand in minutes?

Tools I used:

* [Sequence Diagram](https://sequencediagram.org/)
* [Mind Map](https://coggle.it/)
* [Current Reality Tree](https://www.simplediagrams.com/)

Best of luck mind melding.


