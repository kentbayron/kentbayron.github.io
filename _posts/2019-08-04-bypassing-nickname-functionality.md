---
title: Bypassing Nickname Feature
layout: post
date: 2019-08-14
category: blog
---

# Summary:

Hello Guys, this is my first time to write a blog and I want to say sorry ahead for my bad english.😅 <br>
Last 3 months I found a simple **Logic Bug** one of public program on **Bugcrowd** which I can modify the given nickname to me to any nickname I want. During the account creation there's already a nickname assigned to my account which is designed as unchangable. However I noticed that when changing the details of my account they used JSON format. My guessing instinct was so accurate 🤣 I tried to add **nickname**  parameter and thinking that what if I will make a request with adding **nickname** parameter and see if the **nickname** will change. The JSON request with nickname parameter was accepted in the response. Boom! I can bypass and changed my nickname whatever I want.

# Proof of Concept:
1. Create/signup an account here: [redacted.com](https://redacted.com)
2. Assuming the we have already created an account, now go to [redacted.com](https://redacted.com) and edit your details.
3. Intercept the request and append this parameter called **_Nickname_**

# Orginal Request
{% highlight javascript %}
{
   "name":{
      "given":"redacted",
      "family":"redacted"
   },
   "location":"redacted",
   "bio":"redacted",
   "phone_number":"redacted"
}
{% endhighlight %}

# Edited Request
{% highlight javascript %}
{
   "name":{
      "given":"redacted",
      "family":"redacted"
   },
   "nickname":"bypassed"
   "location":"redacted",
   "bio":"redacted",
   "phone_number":"redacted"
}
{% endhighlight %}

# Timeline
Title of Report: Bypassing Nickname Feature [redacted.com](https://redacted.com)
Date of Report: 11 May 2019 04:43:41 UTC
Date of Resolved: 05 June 2019 12:53:44 UTC
Bounty Paid: **_$50_**

# I hope you enjoy this write up and always remember: <br>**Think outside the box!** <br>
![Thanks](https://media.giphy.com/media/QAsBwSjx9zVKoGp9nr/giphy.gif)

