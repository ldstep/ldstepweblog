---
title: "Re: Running a Personal Website Is Not Fun Anymore"
description:
date: 2026-09-07T11:22:34Z
tags:
   - posts
layout: layouts/post.njk
---

September 7, 2026

I just read Winnie Lim’s post, *[Running a Personal Website Is Not Fun Anymore](https://winnielim.org/journal/running-a-personal-website-is-not-fun-anymore/)*. She writes about the constant barrage of bots, crawlers, and attacks that have made running her personal website a lot less fun.

Her post prompted me to take a look at the firewall traffic for my own site. I’m hosted on Vercel and, to be honest, I’ve never paid much attention to the firewall. I just assumed Vercel was taking care of things in the background.

Looking at the firewall logs, it appears they’re taking care of quite a bit.

Looking at just the past 24 hours, Vercel denied nearly 1,000 requests and challenged another 680. At first I wasn’t sure what to make of those numbers. A lot of the traffic to my site is legitimate automated traffic from RSS readers like NetNewsWire, Feedbin, Feedly, FreshRSS, Reeder, and others.

Then I filtered the firewall traffic to show only the requests Vercel had denied.

Bots were trying to access `.env` files in just about every location imaginable. There were requests for `.git/HEAD`, `phpinfo.php`, WordPress APIs, `xmlrpc.php`, and even a Google Cloud credentials file. My site is a static 11ty site. It doesn’t use WordPress or PHP, so most of these requests never had much chance of getting anywhere.

So I am seeing some of the same things Winnie is seeing. The big difference is that I didn’t know to what extent it was happening. Vercel has been quietly blocking a lot of this traffic before I ever have to think about it.

Maybe running a personal website on today’s web really does mean dealing with an endless stream of bots and people looking for ways in.