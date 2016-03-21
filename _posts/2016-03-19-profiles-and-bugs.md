---
layout: singleblog
title: LAN/WAN switching and nasty 1.1.1 bugs fixed
comments: true
level: critical
---
Uh oh. It looks like 1.1.1 introduced some blocking bugs:

1) For people who are maintaining LAN and WAN profiles, if you try an access an unreachable profile
(example LAN from outside), the app will fail to login but also lock you out of the login screen. Ouch.
Sorry about that. I've released 1.1.2 that fixes this. iOS users won't see it for a couple of weeks
due to Apple's review policy. So please try and do this: When you see the "authenticating" message,
there is a "x" button next to the message - tapping it will put you into login screen. Sorry for the
inconvenience.

2) On the positive side, I've now added support for linked profiles. This goes beyond supporting 
LAN/WAN. You can now specify server profiles as "fallbacks" to other profiles. That means if you have profile A with fallback B and B with fallback C, then zmN will try A - if its not reachable it will try B and if not reachable it will try C.

1.1.2 makes it always easy to know which profile you are currently using:

<img class="img-responsive" src = "/public/images/profilename.png" />

And when you now go to settings, you see a new "fallback" option. Note that to do LAN/WAN switching, specify the LAN profile to be the fallback for WAN and WAN to be fallback for LAN

<img class="img-responsive" src = "/public/images/fallback.png">

Please read full CHANGELOG [here](https://github.com/pliablepixels/zmNinja/blob/v1.1.2/CHANGELOG.md)

