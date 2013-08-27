---
title: The State of Static Sites in 2013
published: true
layout: post
---
I've been a grateful user and big proponent of static site generators for the past few years.

My process has changed significantly over time. From doing things like writing custom deploy scripts, to manually uploading files via ftp. At one point in a previous company we had Jenkins generate and deploy the static site with a post-commits hook from git. 

Many of the initial objections to static sites have been fixed. Here's a rundown of my streamlined process for static sites in 2013.

## Use Jekyll to generate your site

[Jekyll](http://jekyllrb.com/) got a fantastic new [content site](http://jekyllrb.com/) earlier this year. Jekyll is a great solution for a simple blog and it's robust enough to power all of [customer.io's marketing site, docs, and blog](http://customer.io).

### Markdown 

Most posts in Jekyll (including this one) are written in the awesome [Markdown](http://daringfireball.net/projects/markdown/). You can't do everything you can do in HTML in Markdown. On occasion you may want to sprinkle some HTML in your markdown (usually works) or just do the page in full HTML.

### Plugins

One of the best parts of Jekyll is that there are tons of plugins for it. Like this [Sitemap generator](https://github.com/kinnetica/jekyll-plugins) that will help Google index your site. 

## Compass and SaaS for design

You can run two terminal windows when you're developing. One is auto-generating your jekyll site. The other is  generating your CSS from SaaS 

![Two windows](https://www.evernote.com/shard/s28/sh/4d258233-e776-421d-a4d0-8f89ebfe2501/49c7c9d43d9f61379623f476663e3086/res/89d2cd85-aa98-4069-966f-2757ffd1e4cc/skitch.png)

By now you know Twitter Bootstrap, but also consider using the sass versions of [Zurb's Foundation](http://foundation.zurb.com/), or Thoughtbot's [Bourbon](http://bourbon.io/) and [Bourbon Neat](http://neat.bourbon.io/) when building your static site. 

## Pow for displaying static content

If you generate a "public" directory, you can use 37signal's [Pow.cx](http://pow.cx/) to display your static site content rather than using the built in server on port 4000. 

My directory structure is usually:

> project name 
>  - raw
>  - public

Where raw is the normal jekyll files, and public is symlinked to `_site` (the default location jekyll generates its output). This makes it possible to do things like have your local site at `iamnotaprogrammer.dev` rather than localhost:4000. You also don't need to be running jekyll to see it, just to generate changes. 

## Livereload to refresh the browser on changes

Especially for doing styling changes, it's handy to use a [Livereload](http://livereload.com/) to auto-refresh when the site has been regenerated. 

## Deploy on Amazon S3, Cloudfront, Route53

### Why Route53? 

I've used multiple DNS services to attempt to set up stripping the www from my websites. WWW is a relic of a bygone age. In my opinion it kind of makes you look like a n00b if you have it. 

It used to be a huuuuge pain to set this up. I had previously set this up using something called an [ANAME record](http://iamnotaprogrammer.com/Jekyll-S3-Cloudfront-Aname-Root.html).

As of recently Amazon Route53 lets you point www.yourdomain.com at yourdomain.com as something they call an alias.

They also let you point yourdomain.com at a cloudfront distribution by selecting it from a dropdown.

![Selecting from a dropdown](https://www.evernote.com/shard/s28/sh/f07f2357-234c-438a-b920-c6b57677d3e7/b1f309e548edba2e6f8de444e4548f57/res/3a819d30-8832-4e3c-97c1-cf90aa8aa5ff/skitch.png?resizeSmall&width=832)

It's pretty foolproof. And Route53 is very inexpensive.

### Amazon S3 and Cloudfront

Amazon S3 is great for file storage. It wasn't originally designed for hosting content but it works OK for that. Cloudfront is a CDN. Syncing an S3 bucket to Cloudfront makes it ridiculously fast anywhere in the world (theoretically). 

Rather than having your web server that's fast in California be slow for people in Japan, you can use Amazon to make (at least your static content) be fast everywhere.

## Actually Deploying

I had so many hacked together deploy scripts. Now I run one command:

`s3_website push`

[S3 Website](https://github.com/laurilehmijoki/s3_website) is a newer gem that makes deploying to S3 and invalidating your Cloudfront cache for those new files easy. 

I'm tremendously impressed by this gem. It's efficient, checks remote against local for files to delete. However, I'd love to see things get a little faster on pre-processing. 

Overall deploying a jekyll site to S3 and cloudfront is pretty painless these days.

## Dynamic stuff on your site

Here, javascript and javascript apps are your friend. Customer.io's pricing page uses javascript to pull the most recent pricing on to our [pricing page](http://customer.io/pricing). We can update our prices on our app and the static site is up to date.

Most of what you'll want to do is a good solved problem

### Commenting

You *can* do comments on a static site.

I've been using [Disqus](http://disqus.com/) for comments on my sites. However I haven't been happy with how they handle privacy. On a at least one occasion they've opted my blog in to showing other people's content.

I'm most optimistic about progress being made to [use Discourse, new forum software to power comments on static sites](http://trident523.github.io/js-discourseBestOf/).

### Search

I recently heard about [Swiftype](https://swiftype.com/) and I'm really happy with their solution for site search. I had been avoiding it because the projects I had come across were a bit hacky. Swiftype handles indexing your site (and will leverage that sitemap you generated earlier) to come up with a full-text index of your site.

Then you can either use their modal search results or build your own page. I [added search for Customer.io](http://customer.io/search) in a couple of hours one weekend. 

That's it. You now know just about everything I do about doing great stuff with static sites in 2013. 

If there's something cool I missed, or a question unanswered, let me know in the comments.
