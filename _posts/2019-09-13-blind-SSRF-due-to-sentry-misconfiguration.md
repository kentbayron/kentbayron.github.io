---
title: Blind SSRF due to Sentry Misconfiguration
layout: post
date: 2019-11-14
category: write-up
---

# Summary:

Hello Guys, this is my second time to write a blog and I want to say sorry ahead for my bad english. 😅<br>
When setting up **Sentry** you should turn off **Scrap Source Code**. If it is turned on, then the site using **Sentry** will make blind GET requests everywhere controlled from outside via error reporting. During my reconnaissance phase, I found out that the site is using **Sentry** for error reporting and monitoring, refering to this [Hackerone Report](https://hackerone.com/reports/374737). The researcher stated that if the **Scrap Source Code** is turned on, then the **filename** parameter will be vulnerable to Blind SSRF. I tested the parameter and luckily I got callback on my localhost from [redacted.com](https://redacted.com)

# Proof of Concept
1. Intercept all request/response on your **BurpSuite**
2. Search for **sentry** keyword using filters on your **BurpSuite**.
3. Analyze and look for **filename** parameter if there's a sentry request/response. 
4. Change the value inside **filename** parameter to your own localhost server.
5. Wait for the response it will callback to your server.

# Timeline
Title of Report: Blind SSRF due to Sentry Misconfiguration [redacted.com](https://redacted.com)
Date of Report: 13 September 2019 18:24:04 UTC
Date of Resolved: 19 September 2019 22:35:44 UTC
Bounty Paid: **_$300_**

# I hope you enjoy this write up and always remember: <br> **Always read another researcher's writeups**! <br>
![Thanks](https://media.giphy.com/media/MFsqcBSoOKPbjtmvWz/giphy.gif)