---
layout: singleblog
title: zmNinja data consumption in the background
comments: true
---

Hi there, for those of you who have noticed that zmNinja consumes a lot of data in the background, the problem has been fixed.
This is primarily a problem for Android users and not iOS (as iOS freezes the app when it goes to background)

**Summary:** You need to upgrade Zoneminder to 1.29. I submitted a fix to Zoneminder on Jan 29, 2016 which was merged. You can read more about the real problem and the fix [here](https://github.com/ZoneMinder/ZoneMinder/issues/1253).

**Longer Explanation:** 

ZoneMinder streams jpeg images continuously when zms is used over a TCP connection. zmNinja (and any other similar web app) that uses ``img src`` to display images has no control on the TCP object below it. So even if zmNinja deletes the view, Chrome continues to keep the object open and keeps receiving data. zms therefore does not stop streaming because the connection is still on. This is specifically a problem with how Chrome treats these connections (Read [this](https://code.google.com/p/chromium/issues/detail?id=309641).)

So what would happen is zmNinja would continue to build up these objects over time. To work around this, I had to resort to ``window.stop()`` that terminates _all_ connections - not a good idea. So finally, I decided to fix the problem at the server end by adding a command where zmNinja could request zms to quit. Problem solved.

**What it means to  you:**

If you don't have this patch applied, please make sure zmNinja is setup to exit on background (its in Developer Settings). And please plan on updating ZM.
