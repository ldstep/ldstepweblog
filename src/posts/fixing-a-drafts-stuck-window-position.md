---
title: Fixing a Drafts stuck window position
description:
date: 2026-10-11T10:32:43Z
tags:
   - posts
layout: layouts/post.njk
---

October 11, 2026

After using macOS 27's window tiling to put two windows side by side, Drafts stopped remembering its window size and position. Every time I opened it, the window appeared in the left half of the screen. Turning off window tiling in System Settings didn't help.

With some help from ChatGPT, I tracked the problem down to two entries in the Drafts preferences file that still contained macOS `tilingState` information.

The preferences file is located at:

`~/Library/Containers/com.agiletortoise.Drafts-OSX/Data/Library/Preferences/com.agiletortoise.Drafts-OSX.plist`

After giving Terminal Full Disk Access, I quit Drafts, backed up the preferences file, and removed the two saved window settings: `mainWindow.windowFrame` and `secondaryWindow.windowFrame`.

I reopened Drafts, resized and repositioned the window, and quit. The next time I opened it, everything was back to normal.

It's interesting that turning off window tiling doesn't clear the tiling information already saved in an app's preferences.
