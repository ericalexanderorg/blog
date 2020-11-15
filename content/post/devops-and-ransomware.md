---
title: "DevOps and Ransomware"
date: 2020-11-15T13:06:13-07:00
draft: false
---

> Mr. Bezos. I’m all in favor of a clean fulfillment center, but tell me: Why do you sweep? Why do you not instead eliminate the source of dirt? - Unknown “insultant”

Does DevOps pass the “so what?” test? When you start to follow the history of DevOps from Agile, Lean, TOS, TQM, TPS, and beyond; doesn't it lead to plain old critical thinking? Is it anything special? If it's so simple, if anyone can do it, then why on earth would the worlds richest person [pay an “insultant” to teach him](https://youtu.be/O4MtQGRIIuA?t=1250)? Jeff seems to understand that eliminating waste is important, that you should never pass a defect down the line, but he seems to discard the sweeping question as too abstract, and not useful. 

Las Cruces Public Schools (LCPS) may be a perfect example of an organization that’s proud of their ability to [scale up sweeping operations in response to a ransomware incident](https://www.lcsun-news.com/story/news/education/lcps/2020/11/14/las-cruces-public-schools-what-ransomware-attack-taught-us/6296955002/). Why are they so proud of their investment of resources, to deal with ransomware? [How does that support their mission](http://www.lcps.net/district-overview/)? Who’s their customer? Ransomware? If DevOps is just critical thinking and LCPS’ value statement is “[our expectation is that our schools are diverse, equitable, and provide opportunities for the development of critical thinking and democratic ideals](http://www.lcps.net/district-overview/)”, then shouldn’t we hold them accountable for critical thinking?

Nobody gravitates towards DevOps when everything is working. DevOps isn’t valuable in environments where waste is cheap, it’s valuable where waste isn’t cheap. I’d have to think it’s valuable in any public school system that’s struggling to meet demand within their budget. Maybe it’s too late to help LCPS avoid ransomware, but maybe we can help another school system through a little critical thinking exercise.

Most of what people assume is “DevOps” is just repackaged teaching from an Isreali physicist who wrote a book for the business world in 1984. That book, The Goal, [is still popular in business schools](https://slate.com/business/2012/06/the-goal-eli-goldratts-gripping-thriller-about-operations-theory.html). If there’s one thing Eliyahu Goldratt, the author of The Goal, constantly talks about in all of his teaching, it’s understanding cause and effect. Goldratt advocates for the use of what he calls [Current Reality Tree](https://en.wikipedia.org/wiki/Current_reality_tree_(theory_of_constraints)) (CRT) to map out the cause and effect of a problem, the conflict, and where to focus resources on resolution.

Let’s try it out with Ransomware, it may look something like this if we simply map out the cause and effect relationships of what we know about a [ransomware incident](https://thedfirreport.com/2020/11/05/ryuk-speed-run-2-hours-to-ransom/).

![simple cause and effect](/20201115-crt-1.png)


Make sense? Now let’s look at a full current reality tree where we go beyond the ransomware incident and start to look at how a ransomware opportunity was created.

![full crt](/20201115-crt-2.png)
[Full Image](/20201115-crt-2.png)

It balloons out when we start to understand all the vectors of how they get on our network, and what they do, once they get there.

Vectors:
* [Phishing](https://thedfirreport.com/2020/11/05/ryuk-speed-run-2-hours-to-ransom/)
* [Perimeter System: Compromised Credentials](https://blog.malwarebytes.com/security-world/business-security-world/2018/08/protect-rdp-access-ransomware-attacks/)
* [Perimeter System: Missing Patch](https://www.bleepingcomputer.com/news/security/black-kingdom-ransomware-hacks-networks-with-pulse-vpn-flaws/)

Once they get on the network they’ll deploy a [command and control](https://www.theregister.com/2020/09/24/cobalt_strike_cisco_talos/) (C&C) tool that enables them to drop additional tools and start hunting domain admins. They’ll search for servers or computers [where they can login, and where the domain admin is logged in](https://github.com/BloodHoundAD/BloodHound). Once they find that system they grab either the domain admin’s password, or their session information ([just as good as a password](https://en.wikipedia.org/wiki/Pass_the_hash)), then it’s game over. They now have keys to the kingdom and can delete backups and encrypt systems.

Now that you know how it works, and the cause and effect: Did LCPS eliminate the source of dirt? 

This is the only statement that covers what they learned, and how they changed:

>Since then, we have installed firewalls, updated our systems, invested in our teachers and improved our infrastructure so we can protect ourselves.


If we go back to our current reality tree we can ask: 

* Does a firewall address the conflict points? It’s not clear if they’re talking about a new fancy next-gen perimeter firewall, improved network segregation, or host firewalls. Segregation and host firewalls could help if they prevent the bad actor from logging into a shared system where domain admin is logged in.
* Was the problem updated systems? Possible vector if they’re not patching, but it doesn’t address the core conflict.
* Invested in our teachers and improved our infrastructure. Great. Keep it up, but it still doesn’t address the core conflict. 


This is the core conflict:

![core conflict](/20201115-crt-3.png)

The number of domain admins is the core conflict. It’s rarely necessary to have any domain admins, but most organizations have much more than zero when it’s easier to give somebody domain admin access, than it is to take the time to give them only the access they need to do their job. Plain old Least Privilege. Plain old [#4 on the CIS Top 20 security controls](https://www.cisecurity.org/controls/controlled-use-of-administrative-privileges/).

Did LCPS go back and fix the core conflict, or are they still passing a defect downline? What should they have done prior to the Ransomware breach? What can you do now? Evaluate your blast radius. Your InfoSec and/or IT teams should be following the advice of [adsecurity.org](https://adsecurity.org/). They should be running tools like [Plumhound](https://github.com/PlumHound/PlumHound) or [Infection Monkey](https://www.guardicore.com/infectionmonkey/) to understand and reduce blast radius.

You don’t have to be an IT or InfoSec expert to get a glimpse into your ransomware risk. You’re at less risk, possibly near zero, if your organization isn’t using Active Directory; but if they are, you can run the powershell below from your computer to evaluate blast radius.


    # This will install AD tools on Windows 10
    Add-WindowsCapability -Online -Name Rsat.ActiveDirectory.DS-LDS.Tools~~~~0.0.1.0
    # This will list all domain admins
    Get-ADGroupMember -Identity "Domain Admins" -Recursive | %{Get-ADUser -Identity $_.distinguishedName -properties *} | Select Name, Enabled, LastLogonDate, logonCount, PasswordLastSet
    # This will list all enterprise admins
    Get-ADGroupMember -Identity "Enterprise Admins" -Recursive | %{Get-ADUser -Identity $_.distinguishedName -properties *} | Select Name, Enabled, LastLogonDate, logonCount, PasswordLastSet

That powershell will list user accounts ransomware teams are interested in, the ones they’ll go after once they land on your network. Ideally that list is zero. It’s not zero? Shocker! How about passwords? Are they being rotated quickly? Ideally every 7 days or less. What’s the logon count look like? Is it in the hundreds? Ouch, somebody is running around with scissors.

Concerned? Send that output to your IT or InfoSec teams. Ask them if they understand the advice of adsecurity.org or Plumhound. Maybe they have it under control, but maybe they need a little poking to remind them it’s important.

Interested in learning more about the so what of DevOps, and how it applies to Information Security? I’m writing a book. Send me an [email](mailto:devops.book@ericalexander.org?subject=book&body=Let%20me%20know%20when%20it's%20out) or connect on [LinkedIn](https://www.linkedin.com/in/ericalexanderorg) if you’re interested in the book. 
