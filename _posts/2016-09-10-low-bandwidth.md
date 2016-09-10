---
layout: singleblog
title: Low bandwidth love for mobile users of zmNinja
comments: true
---

Hey Mobile users not on WiFi - zmNinja wants to show some extra love for you. This feature is currently available for beta testers (you can join the beta program - see my <a href="http://pliablepixels.github.io/2016/08/12/android-open-beta.html">previous post</a>)

I've just added a "low bandwidth" mode.
<b>Note that this is NOT the same as ZoneMinders low bandwidth mode</b>. I've implemented what makes sense for zmNinja.

<img class="img-responsive" src = "/public/images/sep10_lowbw.png">

When you enable "low bandwidth" it tweaks the settings in montage, event history, event view and live view pages to be significantly more mobile friendly.

When you enable "automatically switch bandwidth", it detects when you are on WiFi or not and automatically switches between regular and low bandwidth modes.

When you are on low bandwidth mode, you'll see an indication like so (note right edge):

<img class="img-responsive" src = "/public/images/sep10_montage.png">

Here are some network graphs as comparisons.

<b>Each run was for a total of 1 minute</b>

Regular mode montage, with 7 HD monitors:
<img class="img-responsive" src = "/public/images/sep10_montage-high.png">

Low bandwidth mode montage, with 7 HD monitors:
<img class="img-responsive" src = "/public/images/sep10_montage-low.png">

Regular mode live view of a HD monitor (1280x960)
<img class="img-responsive" src = "/public/images/sep10_live-high.png">

Low bandwidth mode live view of a HD monitor (1280x960)
<img class="img-responsive" src = "/public/images/sep10_live-low.png">

**So what are the tradeoffs?**

- In montage & event montage screen, monitor quality are at 50%
- In montage screen, refreshes are done at 8 seconds
- In montage screen, monitors won't show alarm state via the alarm API (it will still show alarms if you are using push notification and event server)
- In live view and event view, image quality will be set at 70%

These settings are currently not configurable.
