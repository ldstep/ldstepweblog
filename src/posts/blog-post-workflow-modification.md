---
title: Blog post workflow modification
description:
date: 2026-06-01T14:38:12Z
tags:
   - posts
layout: layouts/post.njk
---

June 1, 2026

Today I simplified my blog post publishing workflow by building a [Drafts](https://getdrafts.com) action, with help from Claude, that writes posts directly to my 11ty posts folder. The idea was to eliminate the manual steps of saving a file to the desktop, opening it in a text editor, adding front matter, and dragging it to the posts folder. 

Getting it to work took some trial and error. The Drafts scripting API has some quirks around file access, and I worked through several dead ends with incorrect `FileManager` syntax and sandbox permission errors before landing on the right approach using a named Bookmark with `FileManager.createForBookmark()`. The action reads the post title from the front matter, slugifies it to generate the filename, and writes the file directly to the posts folder. Tested it on the desktop first, then pointed it at the real posts folder with a bookmark named Posts, and it worked perfectly.