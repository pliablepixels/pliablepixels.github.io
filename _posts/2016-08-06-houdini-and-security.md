---
layout: singleblog
title: The case of missing data on iOS
comments: true
---
<img class="img-responsive" src = "/public/images/poof.png">
[source](http://poster.keepcalmandposters.com/16098.png)

A few iOS users have been occassionally emailing me about the fact that their stored data was disappearing after a while, and they hhad to re-enter things again. While the wizard makes this easier, its no fun having to enter credentials and urls.

Upon investigation, I found the culprit to be <i>where</i> I was storing the data. I was using a data store called 'localStorage' that is essentially a data store area within the context of the browser the app runs in. As it turns out, this data is <a href="http://gonehybrid.com/dont-assume-localstorage-will-always-work-in-your-hybrid-app/">not guaranteed to persist</a> if your phone space starts running low and iOS is particularly agressive in removing this store if space is low.

To fix this, starting the next version, I will be, as a default using SQLite for devices (iOS, Android) and if that is not available, then use localStorage (which will be the case for desktop versions).

I hope with this change, the case of your data playing houdini is put to rest.
