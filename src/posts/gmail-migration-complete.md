---
title: Gmail Migration Complete 
description:
date: 2026-08-15T13:06:06Z
tags:
   - posts
layout: layouts/post.njk
---

August 15, 2026

Since I moved my email [back to Gmail](https://ldstephens.net/posts/why-i-moved-back-to-gmail-from-fastmail/), I’m letting my Fastmail subscription expire at the end of the month. I still get a few emails trickling in from various places to my @ldstephens.com address, so I wanted a way to make sure I don’t miss anything potentially important.

I decided to use Cloudflare’s free Email Routing service. I left the domain registered at Hover but moved its DNS management to Cloudflare. I set up a catch-all so that any email sent to *@ldstephens.com is now forwarded to my Gmail account.
