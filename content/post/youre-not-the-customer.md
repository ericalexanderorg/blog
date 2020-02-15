---
title: "You're Not the Customer"
date: 2018-12-20T07:42:00-07:00
draft: false
---

If you are not paying for it, you’re not the customer; you’re the product being sold. 
@andlewis

If you asked me: What company has full access to __un-hashed passwords__, email accounts, social media accounts and location data, for the sole purpose of monetizing that data, on over 1 million people around the globe? Until a few days ago I’d answer: Google maybe, but don't they hash/salt passwords? 

Let’s back up a bit. Indicators of Compromise (IOCs) are important in security, they’re our canaries in the coal mine. It’s a shame more organizations don’t pay attention to those canaries. I’ll bet your organization is under a continuous [password spraying attack now](https://redmondmag.com/blogs/scott-bekker/2018/03/feds-warn-of-password-spray-attacks.aspx), do you know how to look for it?

An IOC for “Impossible Geographic Logins” on multiple users led me to Edison Tech. The alert triggers when a user logs in from multiple geographic locations they couldn’t possibly be in at the same time.

Something very peculiar surfaced while looking at the login data. It appeared we had multiple users logging in from the same AWS IPs. Why was that? The accounts were compromised and this was a C&C server? It’s easy to jump to conclusions and sometimes it’s best to talk with the users. 

It turns out all 3 users were using the same mobile email client: Edison Email. Don’t mobile email clients store credentials in a secure enclave and connect directly to email servers? Nope.

Edison Email stores your password so it can route all of your data through their servers. They do this to mine your data and sell it. They’re not trying to hide that, they’re transparent about these practices on their [privacy policy](https://www.edison.tech/privacy.html). 

This revelation was mind boggling for me. With over a million downloads this company has access to, and is mining, data on over 1 million people around the world to sell it… and they’re open about it. Take note Facebook.

Transparency and privacy policy aside, let’s look at OSINT indicators of security posture. Any company with this much data, including passwords, is a target. Is data safe there? Just so happens I wrote a tool to help figure that out: [should-i-trust](https://chrome.google.com/webstore/detail/should-i-trust/hocfamfiidomggjegfgenhgaaifjjmla). 

There is no binary rule for attack surface. Every company is a snowflake, they’re all different. There’s troubling signals for edison.tech. Insecure? That’s for you to decide. They’re not patching, and if they’re not covering A9 of the OWASP Top Ten it begs the question: How are they doing on the other 9?

How do I know they’re not patching? Multiple servers running Open SSH 6.6.1 and Nginx 1.4.6. Shodan example: [52.91.185.73](https://www.shodan.io/host/52.91.185.73). They need to be up to OpenSSH 7.7 to fix [CVE-2018-15473](https://nvd.nist.gov/vuln/detail/CVE-2018-15473). They need to be up to Nginx 1.15.6 to fix multiple vulnerabilities including this fun one: [CVE-2017-7529](https://nvd.nist.gov/vuln/detail/CVE-2018-15473). 

While we’re on the subject of attack surface. Don’t expose your SSH servers to the internet. BeyondCorp isn’t a good argument for doing it. Zero Trust doesn’t mean you shouldn’t pay attention to your attack surface. Use a bastion server if there’s a really good need to SSH in from the internet. 

Back to edison.tech. Are they insecure? I don’t know, you decide. 

Here is what I do know:

1) Use MFA wherever possible. It doesn’t solve this problem when services like Gmail & Office 365 offer unique credentials for mail apps but jumping through that hoop is important, it’s a reminder to slow down and think about what you’re doing. 

2) Pay attention to your authentication logs. Send as much of it as you can to a central repository for correlation and anomaly detection. I like Sumo Logic. GreyLog is a great open source solution. 

3) Read the privacy policy. They’re usually short and to the point. Pay attention when a service states “you may provide us with… passwords…” or “We use the Commercial Data we collect to create, share and use Trends research data as described above.” in their privacy policy. 

4) Remember: If you are not paying for it, you’re not the customer; you’re the product being sold. 

Have more questions about edison.tech? They have multiple contact email addresses on their privacy page and they’re very responsive. Thanks Hetal for answering my questions. 
