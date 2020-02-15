---
title: "2019 Breach Trends - Based on Open Source Data"
date: 2020-02-15T09:48:06-07:00
draft: false
---

It’s that time of year again, time to look back on breach data from the previous year, and reflect on trends. A little history is needed before jumping in. I started cataloging breach data about 3 years ago and have tried to capture 3 critical attributes needed to understand the why and the how: How did the actor get access, why did they seek access, and what type of actor were they? The data is far from perfect, but it’s open source. If you see something missing or incorrect, then by all means please submit an [issue](https://github.com/ericalexanderorg/SecurityBreach/issues/new) or edit the data directly through a [pull request](https://github.com/ericalexanderorg/SecurityBreach/compare). 

What's changed since 2018?. We’ve cataloged a little over 2x the breaches in 2019, compared to 2018. That’s not to say there were double the breaches, just that we cataloged double the breaches; again, it’s open source, help out and submit an [issue](https://github.com/ericalexanderorg/SecurityBreach/issues/new) or [PR](https://github.com/ericalexanderorg/SecurityBreach/compare) if we missed something. 

Activity trends are approximately the same when compared to 2018. Breaches surged around November and December in both years. 

![braech trends per month](/2019-breach-trends-month.png)

Curiously, we didn’t capture any cost metrics in 2018. Again, not to say that reflects reality, just means we didn’t capture the data. 2019 cost is still dwarfed by 2017 cost data due to the Equifax breach. 

![cost trends](/2019-breach-trends-cost.png)

Impacted user count is also dwarfed in 2019 by the Equifax breach in 2017. We're headed in the right direction, but not at zero yet.

![impacted user trends](/2019-breach-trends-impacted-users.png)

Broken Access Control still leads the pack for access. The trend is most likely related to organizations struggling with operational changes needed while migrating workloads to the cloud. We’re most likely seeing the results of a removed safety net, the wide area network. The blast radius of a misconfigured system is smaller when it’s isolated behind a WAN, and much bigger when it's exposed to the internet. The finding aligns well with the rise of the hacktivism motive. There’s a new currency to seek out misconfigured systems exposed to the internet and publish findings. Most often that currency is free press for the hacktivist but sometimes it's better described as schadenfreude.

![access trends](/2019-breach-trends-initial-access.png)

There’s an interesting downward trend in compromised valid accounts, it dropped from #1 in 2018 to #2 in 2019, and shows a similar downward trend in 2020 data. I’ll speculate the rise in 2018 was due to the magnitude of easily accessible password dumps, and we're seeing organizations getting smarter about defending against compromised credentials. Password dumps were most likely related, but phishing also had a strong relationship to compromised valid accounts; again, I think we’re seeing organizations getting smarter with better tooling in the form of email filtering, SSO, and MFA. 

![compromised valid account trends](/2019-breach-trends-compromised-valid-accounts.png)

Ransomware is the undeniable growth in motive trends with a 37x increase in 2019. The coincidental downward trend of credit card data may suggest we’re starting to see actors moving on to a path of least resistance found through ransomware. It’s possibly a testament to PCI but also a reminder that the cat and mouse game never ends. We’re lacking in access attribution related to ransomware, so it’s hard to understand trends related to tactics. There’s some signs actors are using old fashioned phishing tactics to land a beachhead while some are simply exploiting published vulnerabilities on perimeter systems. 

![ransomware trends](/2019-breach-trends-money-ransom.png)

PII continues to be a motive, but the why is foggy. I think we’re seeing the remnants of BEC teams seeking data to leverage for money transfer schemes, and there’s also an undeniable trend related to nation state activity. We’re most likely seeing nation state activity related to data required for a better relationship graph, data that can be used to identify espionage and/or political targets. 

![credit card trends](/2019-breach-trends-money-credit-card.png)

Criminal continues to be the dominant actor, followed by hacktivist, and then nation state. The world is flat, not in a flat earther sense, but in the sense that we’re more connected globally than ever. The internet enabled more connectivity for everyone, including criminals, so it’s no surprise that criminal activity continues to lead the actor chart; Hacktivism on the other hand, it’s an interesting trend. Hacktivism tends to break down to: Business seeking free publicity, lone wolfs seeking attention, and a mix of entities seeking to shame another entity. Hacktivism continues to be a great answer to an old question that I think we’ve heard all too often from business leaders: Why would anyone want to hack us? We don’t have _blank_. Turns out they'll do it purely for the schadenfreude. 

![credit card trends](/2019-breach-trends-criminal.png)

That about wraps it up, but like a wise man once said: This is like, just my opinion man. The data is open and you can [go explore](https://ericalexander.org/SecurityBreach/#/), or better yet, you can help improve the data, and in turn make the world a better place through better data that can lead to smarter bets on where to focus defensive security resources.


