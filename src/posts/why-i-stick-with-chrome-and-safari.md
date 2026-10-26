---
title: Why I stick with Chrome and Safari
description:
date: 2026-10-26T09:54:36Z
tags:
   - posts
layout: layouts/post.njk
---

October 26, 2026

I was reading a [forum thread](https://talk.macpowerusers.com/t/safari-as-your-daily-driver-how-do-you-make-it-work-or-did-you-leave/47732/12) the other day and noticed how many people are trying what I'll call third-party browsers: anything other than Chrome, Safari, or Firefox. The pitch is usually workflow: better tab management, split views, built-in notes. Sometimes it's privacy.

It made me wonder: is the security of these browsers equal to Chrome, Safari, or Firefox, or do their users take on additional risk? So I asked Claude. Here's my summary.

Short answer: generally yes, and the risk grows as the team behind the browser gets smaller.

The first issue is patching delays. Most are built on Chromium or WebKit. When a zero-day hits, Google and Apple push a fix immediately. A smaller team has to pull that code, test it, and ship its own release. That gap is an open window, and [AI can now turn a public fix into a working exploit in hours instead of weeks](https://red.anthropic.com/2026/n-days/).

Engine changes are another concern. Sidebars and split panes can require changes to the core engine, which can open holes in the sandbox. Some browsers also weaken phishing checks in the name of privacy.

Trust matters, too. A browser sees everything I do, so its developer is part of my security. A compromised developer account or update server could push malicious code to every user, and an abandoned project can stop updating quietly.

Built-in extras add risk as well. VPNs, wallets, and AI assistants add attack surface, and AI agents can fall for prompt injection from a malicious page.

That said, well-funded browsers like Brave and Edge [usually catch up within days](https://www.pcwelt.de/article/3104349/notfall-update-fur-chrome-stopft-0-day-lucke-im-browser.html), so the risk is highest with smaller forks.

My takeaway: Chrome, Safari, and Firefox are boring, but massive security teams fix vulnerabilities before I even know they exist. When a browser handles my banking and every important account I own, I want security above everything else.
