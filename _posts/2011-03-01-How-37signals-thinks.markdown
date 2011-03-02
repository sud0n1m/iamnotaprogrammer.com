---
layout: post
title: "How 37Signals Thinks"
---

![Basecamp Mobile startup sequence -> Icon, Loading, Project List](/images/Basecamp-Mobile.jpg "Basecamp Mobile Screens")


37signals released [a mobile version of basecamp](http://37signals.com/svn/posts/2761-launch-basecamp-mobile). They opted not to do an iPhone app and focused on building a great mobile site. If you have an iPhone, Android, or Blackberry, [give it a shot](http://basecamphq.com/mobile). It's 95% of what an iOS native app feels like, but it's being rendered by the browser. Their announcement came around the same time that Apple announced it's new rules which would probably mean 37signals would have to share revenue with Apple. [John Gruber has some analysis on that](http://daringfireball.net/2011/03/dirty_percent).

The announcement is interesting reading, but for me the most interesting things came out in the comments:

## On Culture

From Jason Fried (CEO of 37s) responding to a user comment:

> Héctor, this decision had nothing at all to do with not being able to afford iOS and Android developers. We’re fortunate to be in a position to be able to afford anything we need. But there’s more to cost than just money. It’s culture, it’s workflow, it’s a lot of things.
> 
> Fundamentally the decision came down to working with the web, not with native apps on multiple platforms. It came down to flexibility, efficiency, and allowing customers on four (and hopefully more down the road) different platforms to access Basecamp on their phones without having to download special software. They don’t need special software on their desktop machines and we don’t think they should need special software on their mobile devices either. We consider that to be very customer focused and customer friendly.

Any complexity you add to your workflow becomes a pain to manage. 37Signals is adding one more: Mobile. So now they have 2 platforms (with lots of overlap) to build a new feature for. Contrast that with Twitter. They have the web, mobile, android, iOS, blackberry, Windows Phone 7, Mac. So let's say you wanted to add a new feature. You've got to build it and test it in 7 places vs. 2 places. If your goal in life is to prevent your head exploding, the 37signals approach looks pretty good.

## On technology decisions

From SS, a dev a 37s

> Basecamp Mobile is written in [CoffeeScript](http://coffeescript.org/) using our in-house Cinco mobile framework, which ties together [Backbone.js](http://documentcloud.github.com/backbone/), [Zepto](http://zeptojs.com/), the [Eco templating language](https://github.com/sstephenson/eco), and [Stitch](https://github.com/sstephenson/stitch).
> 
> We’ll be talking more about Cinco and open-sourcing it in the coming months.

Is this new framework going to do for mobile what Ruby on Rails did for the web? Maybe. It really says a lot about a company that builds a framework in order to build an app. Rails had a huge impact in how I think about Web Applications, and I'm a Product / UX person. Im looking forward to learning more about Cinco. You can already see the benefits of it when using the Basecamp Mobile.
