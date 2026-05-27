---
title: Bear Notes Export Scripts
description:
date: 2026-05-27T16:53:20Z
tags:
   - posts
layout: layouts/post.njk
---

May 27, 2026

I was bored this morning, so with Claude I built a set of shell scripts to export Bear notes to various locations, triggered via Keyboard Maestro. All scripts query Bear's SQLite database directly at:
`~/Library/Group Containers/9K33E3U3T4.net.shinyfrog.bear/Application Data/database.sqlite`
