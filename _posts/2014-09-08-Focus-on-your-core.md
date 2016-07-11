---
title: 'Mistakes: Too many irons in the fire'
date: 2014-09-08 00:00:00 Z
description: Lessons learned from trying to expand our product
layout: post
---

One of the mistakes we have made in pursuit of growth is expanding our product beyond what we could support.

Last summer through much encouragement from investors and demand from prospective customers, we decided to build integrations with an ecommerce platform and with a payments platform. 

We put Henry (then an intern) to the task of doing these integrations. He managed to do them masterfully and his work there is one of the big reasons we hired him. However, we ended up abandoning and end-of-lifing the work that he did that summer. 

Here’s why. 

## Two groups of prospective customers

We started to notice that there were really two groups of people interested in using Customer.io:


Group 1, let’s call them *DIYs* were content with doing a custom integration with their app. In fact they needed to because their app was custom built and thus their integration needed to be custom. 

Group 2, *Turnkeys* want a plug-and-play solution with their existing ecommerce platform, blogging engine or payments provider. They are sometimes less sophisticated than *DIYs* and may not have in-house developers.

We had built a general tool that provided a lot of flexibiilty for *DIYs* and we were disappointed that we couldn’t provide a better experience for *Turnkeys*. We thought that if we could build a few custom integrations this would help *Turnkeys* use the product and unlock a whole new market for us. 

However, we learned that going after Group 2 wasn’t a smart strategy for us. Here’s why. 

## Increased Complexity

Adding integrations with third parties to our codebase introduced complexity in to our code and service. We had to make sure that those integrations stayed running. We also had to make sure that as we made changes elsewhere in the app, we didn’t inadvertently break the integrations. Someone had to be responsible for the increased complexity from these integrations.

## Increased support burden

Not only did people providing support need to understand our app (already complex as it is), we now needed to provide support for these third parties to help people get them up and running. *Turnkeys*, we found, were generally less sophisticated so even if we got them set up, they often required more handholding to just use the app.

## Splitting the user base

By trying to increase the appeal to *Turnkeys*, we ended up splitting the userbase rather than expanding out from our current user base. The needs of *Turnkeys* were vastly different from *DIYs*. We weren’t serving our core audience better (which small products with few employees should), we were distracting ourselves from our core. 

## Not knowing the customer

We didn’t know *turnkeys* and their needs. Ecommerce companies (the people we had initially thought about targeting) had requirements like seeing past purchases in a structured way, and searching on that data. We didn’t build the right enhancements to our product to make an integration really compelling with their ecommerce platform. We were able to collect all the data, but not make it useful. 

## No organizational support

As a result of all of the above, we ended up abandoning the integrations. We stopped working on them and stopped encouraging people to try them out. At that point in time, it didn’t make sense for our business to do these integrations. 

After this experience, there have been a couple of other times where we’ve overextended and had to pull back. 

A good rule of thumb when evaluating new initiatives is:

**If you’re not willing to commit someones time to the project every day, then you shouldn’t be doing it.**

As our team gets bigger and our product gets more mature, I’d love to circle back to some of the initiatives that we were too early for, but this time I’ll be dedicating people to making them successful. Until then, we’ll focus on our core. 
