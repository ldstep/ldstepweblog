---
title: How to create Custom Actions in Goodlinks
description:
date: 2022-12-29T19:56:55.000Z
tags:
   - posts
layout: layouts/post.njk
---
December 29, 2022

I love [Goodlinks](https://goodlinks.app) as my read-it-later app. Even though I love it and think that its the best reading experience of all read-it-later apps I've still been using Instapaper for its Share All Notes feature. Since I would like to use Goodlinks exclusively, I started wondering if I could replicate this feature with a Goodlinks Custom Action.

The first thing that I had to do was learn how to create a custom action. A google search found nothing on the subject. So I reached out to Ngoc Luu the developer of Goodlinks and he was a great help. I'm going to share our email conversation with you.

Ngoc Lou:

> The sample action in my previous email is not correct, the ' ' character should be changed to '%0A' to create newlines. '%0A' is URL-encoded form of a new line character.
>
> Here is an update of the your Drafts action that will place title, author and link URL in separate lines:
>
> `drafts://create?text=[title]%0A[author]%0A[url]`
>
> You can format the values in Markdown by inserting Markdown format characters in the URL:
>
> `drafts://create?text=# [title]%0A_[author]_%0A[url]`
>
> But this URL will not work because it contains unsafe and reserved characters (whitespace, #), you will need to URL encode them (same as %0A above), so the correct URL should be:
>
> `drafts://create?text=%23%20[title]%0A_[author]_%0A[url]`
>
> GoodLinks already supports a special syntax to URL encode text, it is \{ \}. The text enclosed in those brackets will be URL encoded. You can use them in the URL like this:
>
> `drafts://create?text=\{# \}[title]%0A\{*\}[author]\{*\}%0A[url]`
>
> It is easier to understand and edit. The underscore character is safe, but it is better to URL encode all text (excluding values, e.g: \[title\], \[url\]…) in the URL parameter.
>
> After updating an action, you might need to restart the app in order for the changes to take effect. This is a bug and will be fixed in the next update.

Now that I understand how to create a custom action, I created the following actions to get content into [Drafts](https://getdrafts.com). There's also one for creating a todo in [Things](https://culturedcode.com/things/).

Markdown Title and URL to Drafts

`drafts://create?text=\{[\}[title]\{]\}\{(\}[url]\{)\}`

Title and URL to Drafts

`drafts://create?text=\{# \}[title]%0A\{_\}%0A[url]`

Title, Author, and URL to Drafts

`drafts://create?text=\{# \}[title]%0A\{*\}[author]\{*\}%0A[url]`

Title, Author, URL, and Summary to Drafts

`drafts://create?text=\{# \}[title]%0A\{*\}[author]\{*\}%0A[url]%0A[summary]`

Title and URL to Things 3

`things:///add?title=[title]%0A[url]`

I'm reasonably sure these actions are going to make Goodlinks my only read-it-later app.
