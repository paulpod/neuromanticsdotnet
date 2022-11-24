---
title: Migrating to Hexo
date: 2018-12-17 15:45:10
tags: code
---
Migrating from an old Wordpress and handbuilt personal site to Hexo
===

Did [this pretty much](https://www.netlify.com/blog/2015/10/26/a-step-by-step-guide-hexo-on-netlify/)

Went into my WP admin and exported the site (hmmm, where's the images? I guess we'll find out later).

Then did this [automated WordPress migration](https://hexo.io/docs/migration.html#WordPress)

Picked a [Hexo theme](https://hexo.io/themes/)

Installed [a theme](https://github.com/sergodeeva/cactus-white#install)

Edited the theme a bit, faffed about then removing the actual theme and just copying back the edited files (because it had it's own .gitmodule and I don't know how to fix that).

Oh look all the posts are in there, I'm sure they are all fine - oh, some but not all have their paragraphs all messed up. Ok then, a bit of editing, only 200 odd posts.

Add back some of the images. Intended to add all of them, but that didn't work as planned. Ho hum, review and edit 200 odd pages.

New post: **hexo new "New post title"**

To publish: terminal **hexo generate** and **git push etc** (reminder for myself!)

Deploy to Netlify, worked pretty much first time actually (see theme faffing above).

Chuck in the Netflify DNS servers to Gandi where the domains live. Bosh. Done.
