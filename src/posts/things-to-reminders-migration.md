---
title: Things to Reminders migration
description:
date: 2026-08-03T15:03:52Z
tags:
   - posts
layout: layouts/post.njk
---

August 3, 2026

I watched a video yesterday about moving from third-party productivity apps to Apple's built-in Notes and Reminders, getting ready for Siri AI. The reasoning: Siri AI is going to work best when it's pulling from Apple's own apps, not third-party ones.

I'm not running any open-weight LLMs locally, so when Siri AI ships in OS 27, that's what I'll be using — which means it was time to get my system in order now.

I recently switched all my notes to Apple Notes. Today I switched all my tasks from Things 3 to Reminders.

Reminders has no built-in import, so I figured I'd be doing this by hand. But, before I started, I asked Claude: "I want to get all my tasks in Things into Apple Reminders. Projects, tasks with due dates and notes, and repeating tasks. Can you help me with that?"

Claude wrote a script that migrated projects as lists, along with open to-dos, their due dates, and notes. With a little tweaking, it worked perfectly — the only thing I had to fix by hand was repeating tasks.
