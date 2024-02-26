---
layout: post
title: Speed vs Marketing - Dilemma for the Web
date: 2024-02-26 01:37 +0530
categories: development
---

On the web, there are countless posts that say that there is a huge JavaScript bloat happening to websites all over the world.

Some of the bloat is justified, such as in the Slack app or Trello app, but the most puzzling aspect is its prevalence on *Landing Pages*.

I recently read [this post](https://tonsky.me/blog/js-bloat/) which explained the amount of JS popular landing pages load. Zoom's landing page has 6MB of JS, so does Vercel. Gitlab has 13MB of JS on its landing page. Substack has 4MB, Pinterest has 10MB, Patreon has 11MB.

These are terrible numbers, but why does it happen?

In my experience, this is not something that can be blamed entirely on developers!

When marketing, we love to track everything, and that requires a lot of JS to be loaded. Marketing teams generally ask you to install Google Tag Manager so they can play around with various scripts that help them achieve higher conversion (via popup dialog boxes, subscription boxes, user analytics, etc.).

I am mostly positive that they're aware that this makes the site load slow, but this is a tradeoff they're making, presumably via data.

Does X% drop in users for slow loading website compensate for Y% increase in sign ups? If yes, they will take that deal.

Also, a lot of marketing pages are created and served by a SaaS tool like Webflow. Pretty sure they would be adding a few scripts for themselves.

This does not shift blame entirely from devs though. There are plenty of landing pages that could have been written in simple HTML, but were made with React and bundles of plugins. At the very least, they should educate the marketing team with downsides of bad performance.

But does the market care you're loading heaps of JS? From my experience, answer has been no. 

End consumers try to stick to apps, leaving business users with scrolling websites for their tools. They're scrolling the web with WiFi turned on. WiFi has great speed these days to accommodate these bundles of JS.

So, maybe all this is a pointless debate? IDK 🤷