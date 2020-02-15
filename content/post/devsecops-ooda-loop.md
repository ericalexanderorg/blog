---
title: "DevSecOps - OODA Loop"
date: 2020-01-20T09:06:40-07:00
draft: false
---

How is it a single bad actor could gain access to the data of over 100 million credit applicants when that data should have been protected by a company with the resources of over 45,000 employees? What superpowers did that single bad actor have that none of those 45,000 employees possessed? It turns out that bad actor, Paige Thompson, didn’t have any super powers. It turns out Paige could OODA Loop faster than Capital One and all of it’s 45,000 employees. 

Let’s talk about [what’s publicly known about the breach](https://ericalexander.org/SecurityBreach/#/breaches?filter=%7B%22q%22%3A%22capital%20one%22%7D&order=DESC&page=1&perPage=10&sort=Start%20Date). Capital One had a responsible disclosure program, and along with it a publicly disclosed email address where anyone could report a vulnerability, cool. Capital One received an email through that responsible disclosure process that led them to a public Github repo containing a trove of their sensitive PII - something was terribly wrong. It didn’t take long thereafter for Capital One to realize they had a breach, identify how it had occurred, and remediate.

Capital One was running a WAF (ModSecurity) and that WAF wasn’t configured to prevent a proxy request to the [EC2 Metadata Service](https://www.dowdandassociates.com/blog/content/howto-get-amazon-ec2-instance-metadata/). They had a SSRF vulnerability and Paige Thompson was able to find, leverage, pivot, and access an S3 bucket containing the sensitive PII of over 100 million credit applicants. What would John Boyd think?

John Boyd was a United States Air Force fighter pilot and Pentagon consultant who developed the OODA Loop theory. The theory was born out of John’s studies while searching for predictors of success in aerial dog fights. John hypothesised that in an aerial dog fight the opponent that could observe, orient, decide, and act the fastest would win the fight. Mind blown? OK, so it’s a basic concept with military origins… mind not blown. I wasn’t that excited about it at first either. While it’s just an interesting concept it’s a powerful tool to conceptualize security problems and identify where to focus. 

We can only speculate that if Capital One knew the vulnerability existed they would have Oriented, Decided, and Acted quickly. Capital One probably needed to reduce their Orient lead time, and from there we can disect further by asking exploritoray questions like: 

* Did their staff understand SSRF vulnerabilities?
* Were they resourced to find SSRF vulnerabilities?
* Were they effective at finding SSRF vulnerabilities?

Did their staff understand SSRF? Capital One probably deals with more regulatory, contractual, and compliance initiatives than most security practitioners will see in their entire career; it's almost guaranteed they ahd staff with knowledge of SSRF, in that environment. They have no shortage of people with “information” & “security” in their Linked In profile and they currently have 31 open positions related to information security in the UK alone. Somebody there had to have understood SSRF, probably not the problem.

Were they resourced to find SSRF vulnerabilities? They had a Senior Manager for Vulnerability / Configuration Management who advertised their tooling to [Build a secure AMI bakery](https://www.qualys.com/customers/success-stories/capital-one-building-security-devops/). Check that box, they were resourced, and potentially looking for SSRFs. 

Were they effective? No, they didn’t catch the SSRF vulnerability. OK, so I wasn’t there and I don’t know what really happened. The best-laid plans of mice and men often go astray and while none of us want to fall down with a security breach, there’s a learning opportunity here for all of us. 

Do you know if a SSRF vulnerability exists in your environment? Is it on infra exposed to the internet? Given any of your internet facing infra: If it's compromised, where can the bad actor pivot? There’s tooling out there that can help your team observe faster, some [commercial](https://jupiterone.com/), and some [open source](https://github.com/lyft/cartography). 

Have fun [OODA Looping](https://csrc.nist.gov/CSRC/media/Presentations/The-Cyber-OODA-Loop-How-Your-Attacker-Should-Help/images-media/day3_security-automation_930-1020.pdf)

