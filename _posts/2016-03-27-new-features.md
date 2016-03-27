---
layout: singleblog
title: More love to timeline and alarms with 1.1.3
comments: true
level: critical
---
Hey there! 1.1.3 is around the corner. Several updates that may interest you:

<h3>Reachability woes</h3>

So in 1.1.1 and .2 I added an option to be able to connect to multiple servers as a fallback. As it turns out, for a certain section of folks, especially those using SSL, this resulted in connections failing. Yikes! I use SSL as well but never managed to replicate this issue. That being said, more than one person reached out to me, so it must be a problem. I am hoping I have fixed this in 1.1.3. Instead of just releasing it, I am going to take a couple of weeks beta testing with the affected users, lest it breaks something else. Network issues are always hard, especially if I can't replicate them. 

**If you are using 1.1.2 and are facing reachability issues, please send me an email to pliablepixels at gmail, with the mobile platform you are using, if you want to beta test 1.1.3 and check if this feature works for you**. I'll only respond to the first 5, so my apologies if you don't get a response.

<h3>Hide Monitors introduced again</h3>

Older versions had the ability to hide/show monitors in zmNinja. That feature disappeared after the new drag and drop montage came in. Well, the feature is back - you will now see an "eye"-con at the top of montage screen

<img class="img-responsive" src = "/public/images/mar27_2015_hide.png">

<h3>Alarm Frame navigation</h3>

One of the good things about the old event player was that you could scrub the slider around and navigate to a specific frame during event playback. It also had alarm markers. However, it was still hard to point to an exact alarmed frame. And then with the new event playback (via zms) mechanism, that feature completely went away (in return for more stability). So now, I've added a new feature to event playback. see the "alarm" icon below? 

<img class="img-responsive" src = "/public/images/mar27_2015_alarm.png">

When you tap on it, you get this:

<img class="img-responsive" src = "/public/images/mar27_2015_alarmnav.png">

You can use this window to navigate alarms more precisely, and while we are at it, save it to disk too

<h3>More Timeline Love</h3>

zmNinja has a cool timeline which you can pinch and zoom, but I know, its not as effective as the ZoneMinder timeline. There is a simple reason for that - there are significant DB operations that go into showing what ZoneMinder shows and that code runs in PHP (that is, at the server end). Doing this in zmNinja will overload ZoneMinder, which is why I can't offer the same function as of today.

However, that doesn't mean it can't be improved:

<h4>Alarm count</h4>

A simple enhancement to the timeline now shows how many alarm frames are present in a timeline slice, like this:

<img class="img-responsive" src = "/public/images/mar27_2015_timeline_count.png">

<h4>A whole new view</h4>

Saved the best for last!
Timeline now has a **new screen** on double-tap. Double tap an element
and you get:


<img class="img-responsive" src = "/public/images/mar27_2015_timeline.png">

Double-tap to exit. What do you think?

