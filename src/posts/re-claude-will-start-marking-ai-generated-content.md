---
title: "Re: Claude will start marking AI-generated content"
description:
date: 2026-08-12T09:13:55Z
tags:
   - posts
layout: layouts/post.njk
---

August 12, 2026

I saw [this](https://support.claude.com/en/articles/16266773-how-claude-marks-ai-generated-content) in my RSS feed this week. It caught my attention, so I wanted to learn more about it.

> **Embedded watermarks in text** 
> 
> When a supported Claude model generates text, it weaves an imperceptible watermark directly into the text itself. You won’t see it, and it doesn’t change the meaning, quality, or readability of Claude’s response. 
> 
> Because the watermark is part of the text, it will travel with the text when it’s copied and pasted elsewhere, and may persist through some editing. Watermarking will be applied at the model level, which means it will be present no matter which Claude product or surface the text comes from.
>
> […]
>
> **Detecting Claude’s marks** 
> 
> We’re also working to enable users and other third parties to detect Claude’s embedded watermarks and provenance metadata. Detection checks whether a piece of text or a file carries a supported Claude mark. If a supported mark is found, it indicates that the content may have been processed by Claude.

I haven't used Claude for proofreading my text; for that, I use EditGPT. But I do use it for vibe coding automation scripts and maintenance of my 11ty site. Since code is text, though, I wonder if they will embed invisible characters or byte sequences between visible characters as well?

John Gruber discusses the problems with embedding invisible characters or byte sequences between visible characters:

[Anthropic Posts ‘How Claude Marks AI-Generated Content’ Without Explaining How Claude Marks AI-Generated Content](https://daringfireball.net/linked/2026/08/11/anthropic-claude-watermarks)

> A string of text is just one character followed by another. At first I presumed that Claude is going to start “embedding” invisible characters/byte sequences between visible characters — which would unavoidably cause immediate problems.

If this interests you, I encourage you to read John's post in its entirety.
