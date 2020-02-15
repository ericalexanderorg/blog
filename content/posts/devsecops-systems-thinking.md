---
title: "DevSecOps - Systems Thinking"
date: 2020-01-08T17:36:14-07:00
draft: false
---

Every system is perfectly designed to get the results it gets - W. Edwards Deming

Seems most in the tech world have heard of DevOps, but never Deming - the father of quality. Deming’s ideas were the catalyst for Lean Manufacturing, and in turn DevOps to DevSecOps. While many of us have heard “Security is everyone’s job” we don’t know it’s borrowed from Deming’s quote: Quality is everyone’s job. Did you know he was primarily addressing management with that quote? 

It’s unfortunate the saying “Security is everyone’s job” gets thrown around like everyone doesn’t take security seriously, like there’s some kind of rampant normalized deviance or cognitive dissonance problem when in reality the problem is many times closer to a cognitive load issue. Phishing is a great example. What do you think? Is phishing more normalized deviance, cognitive dissonance, or cognitive load?

Ever sit down and talk with somebody that’s fallen for phishing? Ever ask them why they opened that funny looking doc attachment or clicked on that link and entered their username and password? Most often you’ll hear words like busy and confused. Most of the time they’re multi-tasking, most of the time they don’t realize how far into auto-pilot mode they’ve drifted. 

Deming promoted the idea that you need to understand the system to understand the outcome and in any sufficiently complex system the only way to achieve a desired outcome change is to experiment. Toyota changed it a little and talked about conditions: Current and Target conditions. If you’ve been exposed to Agile Methodologies, then you’ve probably heard of user stories as a way to take customer discussions and requirements and translate them into a description of desired functionality for engineering to build. Target conditions aren’t much different, they’re descriptions of a “north star”, a situation that you’d like to be in, with no definition of how you’re going to get there. 

Current condition is your hypothesis about your current condition. Wait, hypothesis? I don’t know my current state? I don’t know what’s going on? Probably not. Bear with me, it’ll all make sense. I promise. 

So now you’ve got this hypothesis of reality, point A, and this idea of what you’d like reality to look like, point B. How do you get from point A to point B? Let’s use that phishing example. Let’s say our target condition is to always avoid anyone clicking on a phishing link they received in an email, and let’s say our current condition is, well, it’s ridiculous how often idiots click on those links! 

The next step? It’s to hypothesize what action will get us closer to our target condition. Wait, idiots right? These idiots need some training. So that’s what we do, but we want to keep experiment steps short, we want to fail fast, so we take our top idiot and set them down for a day of training on how to spot a phishing email. The next day check if it worked by sending them some mimicked phishing emails to see if they fall for it. 

Didn’t work. Turns out there was no measurable improvement. Training didn’t work, what else can we try? Everyone keeps saying they’re “busy” or “confused”, how do we reduce busy & confused? We need a cup of copy to think it over so we head down to the new fancy espresso machine in our break area. As we’re trying to figure out how to use this espresso machine that only an engineer could understand! It hits us: Maybe it’s a design issue?

We hypothesize that we can decrease cognitive load by adding a warning to the email messages when there’s phishing indicators. We run the idea by the team who manages the email system and they’ve got some ideas on how to make it work. The next day we’re testing it out and it’s a success. Turns out it wasn’t an “idiot” problem, turns out they really were just busy and confused - it was a cognitive load problem and a little feedback in the UI solved the problem.

OK, so it’s all a little contrived, but you get the idea. We just went through the Deming Cycle: Plan, Do, Check, and Act. It’s not magic, it’s just a simple technique to iterate towards improvement in a complex environment or system. The technique depends on little to no assumption that we know all factors, but as we loop, we learn. Our mental models of the system improves as we loop and we become more effective and efficient through every loop.

