# Instagram Open Redirect Vulnerability (2026-March)

This is the real URL: https://www.instagram.com/accounts/onetap/?next=%2Fhiru.adi

The `next` query parameter is vulnerable to open redirect, which means that an attacker can craft a URL that redirects users to a malicious site. For example, an attacker could create a URL like this: https://www.instagram.com/accounts/onetap/?next=plzhack.me. It would take you to [www.instagram.complzhack.me](http://www.instagram.complzhack.me).

Also, not having any value passed into `next` like: https://www.instagram.com/accounts/onetap/?next= will take you to: [www.instagram.comundefined](http://www.instagram.comundefined).

`plzhack.me` is a domain that I used for testing purposes, and it is not malicious. I went ahead and added a DNS record to point `www.instagram.com.plzhack.me` to my own server to demonstrate this vulnerability. 

I will now update this URL to https://www.instagram.com/accounts/onetap/?next=.plzhack.me - this will take me to [www.instagram.com.plzhack.me](https://www.instagram.com.plzhack.me/), which is a domain that I control.

- Demonstration (Video 1): https://youtu.be/i2dAXSxiMAw
- Demonstration (Video 2): https://youtu.be/WUxoPe7h0a4

This way, attackers can redirect user's into their own malicious sites, which can be used for phishing attacks or to distribute malware.

However, as seen in the demontration videos, it does require some user interaction. It requires the user to press on "Save info" button - which most less security conscious people do.
