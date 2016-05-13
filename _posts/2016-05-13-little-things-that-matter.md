---
layout: singleblog
title: Arming/Disarming and other things that matter
comments: true
level: critical
---
Hey there, a quick peek for the next release. 
I'm focussing on improving usability. There are many things cleaned up in the backend of the code that you will not see, but will lead to general responsiveness and stability improvements. But lets talk about what you will see:

<h3>Arm/Disarm Monitors</h3>
You've been asking for this for a _long_ time. Well, you can now arm or disarm a monitor right from zmNinja. Note however that this needs updated APIs which will be part of the next release of ZM (not available in 1.29). So I need to wait before I release it. Here is how it looks:

<img class="img-responsive" src = "/public/images/arm.png">

<h3>What are my monitors doing?</h3>
The other thing you'd really want to know, say in montage screen, is are my monitors recording, alarming or idle?
For those who are using the [Event Server](https://github.com/pliablepixels/zmeventserver), you already get alarm notifications but they are really meant to serve as an instant notification and go away after a while. And how about folks who don't use the event server? Well, you will now see dots in the montage screen like so:


<img class="img-responsive" src = "/public/images/arm_status.png">
See the green and red dots? That says my front door camera is in "record" mode, but not alarmed mode. (Mocord/Record). While the red dot in my garage says there is an alarm being recorded. You will see this status in single view monitor mode too (as you saw in the image above)

<h3>Button layout cleanup</h3>
The other thing you would have noticed in the first image is the neat stack of grey buttons - previous versions of zmNinja had independently positoned buttons that could overlap as well (example, if you are running in a Desktop mode version watching a live feed and an alarm occurred, the alarm notification overlaid the zoom buttons). Not good. This was clumsy coding really. I fixed that - I've converted them to neat lists so no matter what buttons show (or don't show), overlaps should be gone. I'll eventually get around to doing the same thing for the preset and PTZ buttons (which may still overlap)


<h3>Multi-server love</h3>
For those using the venerable new multi-server feature, the next version fully supports it. Including video MP4 playback. Note that video playback has various limitations due to ZM not supporting certain features like prev/next etc.

<h3>Wizard</h3>
I know, there was a [dedicated](http://pliablepixels.github.io/2016/05/01/wizard.html) post on this. But its really awesome and worth mentioning again. This is a big step towards simplifying configuration.




