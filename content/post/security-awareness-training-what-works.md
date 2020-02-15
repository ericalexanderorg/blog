---
title: "Security Awareness Training - What Works?"
date: 2018-01-27T15:01:50-07:00
draft: false
---

Need to be PCI, CJIS, or NIST 800-53 compliant? If so, Security Awareness Training (SAT) isn’t optional. What if you’re not bound by those security requirements? What if you could take a pragmatic approach and do it, not because you have to; rather, your only motivation is to reduce risk.

Let’s say you’re launching a new cryptocurrency exchange. You’re not bound by any compliance requirement, but, you’re also a major target. In fact, you’ll probably be more of a target than any company bound by PCI, CJIS, or NIST 800-53. [The] (https://www.coindesk.com/tether-claims-30-million-stable-token-stolen-attacker/) [proof] (https://www.bleepingcomputer.com/news/security/hackers-hijack-dns-server-of-blackwallet-to-steal-400-000/) [is] (https://www.wired.com/2014/03/bitcoin-exchange/) [in] (https://threatpost.com/breach-bitcoinica-exchange-nets-87000-online-currency-051412/76559/) [the] (https://www.ccn.com/bitcoins-price-plummets-125k-bitcoins-may-stolen-bitfinex/) [pudding] (https://www.ccn.com/new-details-emerge-bitstamps-5-million-bitcoin-hack/). 

OK, so you need to protect your data and have no compliance requirements. It's a unique advantage in that you can grocery shop compliance requirements. You can pick and choose what works and what doesn't. 

You’ve got plenty to think about and one is Security Awareness Training. Your research starts with reviewing what’s out there. Google “filetype:pptx “security awareness training” and you find most training distils down to about 4 topics: 

* Password Management: How to choose a good password and secure it
* Email/Phishing: How not to fall for phishing 
* Browsing: How to avoid malware and data spills
* Privacy: Definition of sensitive data and how to protect it 
* Role Based Training: Policies and procedures specific to a group. 

Time out. Let’s talk about how our brains work. 

>“Until you make the unconscious conscious, it will direct your life and you will call it fate.” -Carl Jung

We like to think we’re in control all the time. Truth is, our brains are on autopilot most of the time. Our brain wants to sort into buckets when making choices. It wants to do what worked last time. Email from IT asking me to do something? Just follow the instructions and get it over with. Excel asking me to trust a document? Yeah, it always does that, just click OK. 

Like it or not, we’re conditioned. At work we’re conditioned to be efficient, to get things done. Stopping and thinking about every action - it’s not efficient and nobody’s getting rewarded for slowing things down. We’re rewarded for doing more in less time. 

Back to SAT. Which of the common SAT topics are going to trigger “slow down and think about it”? Arguably, none of them. 

Let’s break each one down
Password Management
--------------------------
This is the idea that we can tell users how to create a really good password and how to protect that really good password. Where’s the carrot? Where’s the stick? The carrot is “easy”. The stick is password enforcement when they choose a password. Without the stick they’ll choose easy, the pavlovian response. 

Training isn’t an answer to this problem. Enforce password policies on the systems you maintain and make a good password manager available to your users that can help enforce your password policy on sites you don’t manage. Need a password policy? NIST has some great guidance [link]

Email/Phishing
--------------------------
This is the idea that we can tell users to not fall for phishing emails. It doesn’t work. It was proven by a west point study but you can do your own study. 

I’ve done this many times and it always yields about a 40% response. Keep in mind, we need a 0% response to be successful. If I’m an attacker my beachead is 1 PC on your network and from there I’ll pivot to what I want. 

Run a group of people, ideally more than 10, through very traditional phishing email SAT, then, tell them you’ll send a phishing email next week. Find an a recent phishing example, mimik it, and send it to your sample group. 

About 40% seems to be the magic number of those who fall for it. Why is that? My theory: About 40% are going to be right brain dominant. They’re on autopilot when responding to email.

So what’s the better solution? 

Start with a good email filter service. A good filter service will weed out most phishing emails. Out flank the ones that do. They want passwords? Use MFA. They want wire transfers (CEO fraud) establish operational controls that require out of band verification. They want you to install malware? Use decent endpoint AV and network isolation to protect your high-value data. 
Browsing
--------------------------
It’s impossible to demonstrate every possible browsing scenario in memory training. Most people have no idea what a TLS error is trying to tell them or what domains they should be entering passwords in. They’re conditioned to blindly bypass any feedback when something's wrong. 

The technical solution is the same as the phishing threat: Out flank your advisory. Know what they’re after and limit their access at every turn through controls. 
Privacy
--------------------------
This is the one area that SAT is part of the solution. This is where we educate users on the data they need to be the most focused on protecting and what they can do to protect it. 

If what you’re protecting is 100% digital than there are plenty of DLP solutions that can help. If you’ve got hard copies then DLP isn’t going to solve the problem. 

SAT is a good tool here but constant feedback is better. Posters around the office can serve as reminders regarding what PII is and how to protect it. Keep it fun. You’ve got to win hearts and minds to make it work. 
Role Based
This is where SAT makes sense. Where possible you should be using immediate feedback in your process to ensure consistency. You should also educate high value roles of their value: C-Level execs and systems administrators are typically the highest value from an attack perspective.  Sys Admins have elevated access to systems if not the keys to the kingdom. C-level execs have access to high value data. Finance, HR, and Support may also be high value targets in your organization. 


>You can’t manage what you don’t measure. - Peter Drucker

You’ve got to quantify return on investment. Regardless of what you’re pushing through SAT you’ve got to make sure it’s providing value; otherwise, why’d you waste everyone's time?


