---
title: Verizon made an enemy tonight
date: 2014-07-17 00:00:00 Z
description: Why netflix is slow on verizon fios and how to fix it by using a VPN
layout: post
---

On a flight back to New York I read Level 3's assessment of the latest round of the [Netflix vs Internet Provider debacle](http://blog.level3.com/global-connectivity/verizons-accidental-mea-culpa/).

The summarized version is that basically Netflix is slow because Verizon refuses to add capacity to peer with Level 3. Fixing the situation would cost Verizon on the order of a few thousand (that's right thousand) dollars. Level 3 is even willing to foot the bill. But Verizon refuses. 

## Is Netflix actually slow on Verizon Fios?

I wasn't sure how to test my Netflix speed. After a bit of googling I found an article by Wired [on how to test your Netflix streaming speed](http://www.wired.com/2014/06/netflix-streaming-test/). I followed their steps and I was shocked.

The video on netflix actually shows you how fast it is streaming to you which is helpful for ddiagnostics. 

[Here's the test video on Netflix for quick reference](http://www.netflix.com/WiMovie/70136810)

Keep in mind, I pay Verizon for 75 mbps down, 35 mbps up on my Fios connection. 

This Netflix video streams at 375 kbps (or 0.375 mbps -- 0.5% of the speed I pay for) at the fastest. I was shocked. Then I decided to try connecting to a VPN service to compare. 

## Can a VPN make streaming Netflix faster?

My hypothesis here was that by connecting to a VPN, my traffic might end up getting routed through uncongested tubes. Basically, if Verizon is not upgrading the tubes that go to Netflix, maybe I can connect to a different location (via VPN) first where Verizon will have good performance and there will be no congestion between location 2 and and Netflix.

Was I successful?

Here's a recording of my test:

<iframe width="640" height="480" src="//www.youtube.com/embed/5vs3QhEx_3w?rel=0" frameborder="0" allowfullscreen></iframe>

Watch the video to feel the full pain. What you'll see is that on Fios it streams at 375 kbps at the fastest. The experience sucks. It takes an eternity to buffer. 

Then I connect to a VPN (in this case [VyprVPN](http://goldenfrog.com/vyprvpn)) and I quickly get up to full speed at **3000 kbps** (the max on Netflix), about 10x the speed I was getting connecting directly via Verizon.

## The bastards...

It seems absurd to me that adding another hop via a VPN actually improves streaming speed. 

Clearly it's not Netflix that doesn't have the capacity. It seems that Verizon are deliberately dragging their feet and failing to provide service that people have paid for. Verizon, tonight you made an enemy, and doing my own tests have proven (at least to me) that you're in the wrong here.

But, luckily I'm resourceful and can usually solve my own problems.

## How to keep the VPN connection open

We sometimes watch netflix on the TV, sometimes on the iPad. I didn't want to have to think about how we connected, so I wanted to find a way to connect the router to the VPN so it would be always on. 

I bought an [Asus RT-AC66U](http://www.amazon.com/gp/product/B008ABOJKS/ref=as_li_tl?ie=UTF8&camp=1789&creative=390957&creativeASIN=B008ABOJKS&linkCode=as2&tag=onmacnet-20&linkId=DOVUJMQIULQUBRVF). I really like this router and it works a lot better than my old Airport Extreme. However, in order to connect it to a VPN, I had to flash it with a [custom firmware from some wizard named Merlin](http://www.lostrealm.ca/tower/node/79). 

After updating the router, you'll now have a screen where you can connect to a VPN and tell the router to always be connected. 

![Asus Router Config](/images/Asus-Router-Openvpn-Config.png)

If you're using VyprVPN, you can [grab an OVPN file](https://www.goldenfrog.com/support/vyprvpn/vpn-setup/ipad/openvpn-connect) for a server near you and upload it to the router where it says "Import ovpn file". 

If you have a different router, there's also [Tomato](http://www.polarcloud.com/tomato) and [DD-WRT](http://www.dd-wrt.com/) as alternative firmware.

## Problem solved

So in the space of about an hour, I got furious at Verizon, found a way around the problem, and then fixed it for good (for my household).

Nothing quite motivates me like when something shouldn't be the way that it is.

## Updated with more tests 

Some people mentioned that 3000 kbps wasn't the max for Netflix. That's a limitation with Netflix on a Mac. Since I now have all traffic going through a VPN, it was easy to test on other devices.

### On a Roku

Here's the test video loaded on my Roku. Even the cat likes things better at 5800 kbps:

![The netflix test on a roku](http://fast.customer.io/s/5800-kbps-netflix-on-roku-vpn.jpg)

### On a Windows 8 PC running the Netflix App

Same test on my Windows 8 box running the Netflix App. 

![Netflix test on a pc](http://fast.customer.io/s/Netflix-Windows-8-verizon-vpn.jpg)

## Your turn:

Netflix subscribers: [What happens when you do the Netflix test?](http://www.netflix.com/WiMovie/70136810). Do you max out at 3000 / 5800 kbps? Or struggle to even play the video? 

I'd love to know in the comments. 
