---
title: Claude saved me hours of link cleanup
description:
date: 2026-04-28T14:37:52Z
tags:
   - posts
layout: layouts/post.njk
---

April 28, 2026

Today I was working on a blog project collecting a bunch of post links to use in another project. When I need to visit a lot of posts on my blog, I do it through a localhost:8080 version of the site instead of the live one. I run an AppleScript that opens it in Terminal:
      
 ```applescript
set projectPath to "/Users/lorenstephens/Documents/GitHub/ldstepweblog"
tell application "Terminal"
	activate
	do script "cd " & quoted form of projectPath & " && npm start"
end tell
```
   
This fires up the Eleventy dev server and serves the site locally at localhost:8080. So what I ended up with was a list of markdown links that looked like this:

`http://localhost:8080/posts/why-write-when-no-ones-reading/`

To use them in the new project, I needed to swap `http` for `https` and `localhost:8080` for `ldstephens.net`. A lot of manual work. On a lark, I asked Claude to handle it and it built a small interactive widget right in the chat: paste your list, click a button, copy the corrected output.

Three minutes with Claude saved what would have been a couple of hours of manual work.
