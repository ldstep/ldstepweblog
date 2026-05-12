---
title: Refining my file-over-app workflow
description:
date: 2026-05-12T14:14:15Z
tags:
   - posts
layout: layouts/post.njk
---

May 12, 2026

I’ve been refining my file-over-app workflow lately.

For things like blog posts, daily notes, journal entries, and notes, I prefer working in a markdown text editor. In my case that’s [MarkEdit](https://github.com/MarkEdit-app/MarkEdit). At the same time, most of the ideas and thoughts that eventually become those things start in [Drafts](https://getdrafts.com).

Of course I could do everything in Drafts, but I’ve realized I don’t actually want to write there long term. I like it better as a capture tool than as a writing environment. What I’ve settled on is using each app for what it does best.

If I intentionally sit down to write something, I’ll usually start directly in MarkEdit. If it’s something I captured quickly in Drafts, I use actions to send it where it belongs as a markdown file.

For blog posts, I have actions that save drafts into either an Ideas folder or a Drafts folder. Notes work the same way. If something is clearly a note, the action sends it straight to my Notes folder.

Daily notes and journal entries work a little differently. Those actions append the contents of a draft, along with a timestamp, into the appropriate markdown file. The journal action appends to a monthly journal file while the daily note action appends to that day’s note file. If the file doesn’t already exist, the action creates it automatically.

What I like about this setup is that it keeps capture friction low while still letting me write in the environment I prefer. Drafts becomes the place where text starts while markdown files become the long-term storage layer.

It also avoids the feeling of being locked into a single app. The apps are really just interfaces for different stages of thinking. Drafts handles capture. MarkEdit handles writing. The markdown files are what actually matter.
