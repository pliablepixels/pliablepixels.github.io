---
layout: singleblog
title: Time without TimeZone is meaningless!
comments: true
---

So 1.2.27 made many useful tweaks, including the super useful relative time, that gives you "humanized" time relative to current time - like "this event occured 3 minutes ago". Awesome!  Until I got <a href="https://github.com/pliablepixels/zmNinja/issues/353">this</a> issue report on github. Essentially, zmNinja was telling this user an event occurred in the future!
That's because he was in a different timezone that was behind the timezone where ZoneMinder is installed.

While this is funny, imagine the opposite. You are on travel, your house is being broken into and your event time says it occurred an hour ago due to Timezone differences - thats serious.

While this was fine earlier, apps like zmNinja has drastically increased access of ZoneMinder via phones. And people with phones often travel. One of the most common use-cases I keep hearing from my users is they have company executives who want to see cameras on their phones while on travel. Time without timezone conversions here could be problematic.

Well, the problem is that ZoneMinder doesn't provide any TimeZone information at all. It simply doesn't store any timezone data in any of its event data, so its impossible to know the timezone remotely, unless you force configure it, which is crappy.

So I went ahead and added TimeZone API support for ZoneMinder - you can replace your ZoneMinder `HostController.php` file  with <a href="https://raw.githubusercontent.com/ZoneMinder/ZoneMinder/master/web/api/app/Controller/HostController.php">this</a> one. (Caution: Do this only if you are on ZM 1.30). This will be part of the next release of ZM, whenever that is made.

Once you add TZ support in ZM, the next version of zmNinja will automatically detect your local timezone and display events relative to your local current time.

When you tap on the menu icon, you'll also see what you local and server timezone are like this:
<img class="img-responsive" src = "/public/images/oct21-tz2.png">

You will also see a new "Developer Option" that is automatically turned on. You can turn it off, if you don't want it enabled.
<img class="img-responsive" src = "/public/images/oct21-tz1.png">


