---
title: Designing Websites and CSS for Sony's PSP
url: 111.html
id: 111
comments: false
categories:
  - design
date: 2005-07-31 15:35:36
tags:
---

I spent a while looking around online and couldn't find anything about adapting websites to work well on the new Sony PSP browser so I guess I'll write it myself. It's a good browser with broad and accurate CSS support for a handheld. It's also going to sell lots of units and be an important test browser, with over 5 million sold already, and not even released in Europe **for another month still**. Bloody Sony... but I digress. 

Having just spent a day re-working this site there are a few key notes worth recording. 

1) The screen width with is very tight, 480 pixels I think. Once you've got a brandmark top left and some navigation in there don't expect any space to spare. 

Consider small pixel font nav graphics to maximise this. Keep them trim. Every pixel counts! 

2) The sans-serif face is quite open and easy to read, but large - much larger than the serif face - so be careful about balance. 

3) Memory is tight - I have had a few out of memory errors loading pages with many images or very long blog-style content layouts. Keep it short. 

4) Make it a liquid layout that scales with the browser window width if you can. Use percentages to make the layout work, use max-width to keep the page to a sensible width in PC browsers. Use [this hack for IE](http://www.svendtofte.com/code/max_width_in_ie/) to handle max-width too. 

5) Trim out scrappy code, comments, whitespace. Keep image alt tags _short_. It ain't a quick browser. 

6) It supports iframes! Very handy for making inlne content changable and interactive without reloading and rescrolling a whole page. 

7) Do not get annoyed and throw the PSP across the room when it fucks up. Ahem... 

8) Being almost 2:1 widescreen the screen is very different to what we usually design for, so make use of this and try splitting your content into columns. 

9) If you are not going for a liquid layout, stick your advertising far right and expand your navigation into direct content links on the left. 

10) Trim your body margins, especially the top. Wasted space is a bit rude at this level. You'll notice most of these points are good general points for using CSS anyway, and indeed re-working Bunker along these lines finally gave me a liquid layout and broad compatibility with IE and firefox, etc. 

I've been a bad man and avoided some of these points for a long time now, usually for reasons of design-first (and more specifically a 3 or 4 column page) but I repent now because the PSP browser is important enough to warrant the compromise.

_Update:_ Apparently the browser is a NetFront browser by Access. [More info](http://www.psp-vault.com/modules.php?op=modload&name=News&file=article&sid=244). I had fun extreme pain with this when doing some SVG work for Vodafone last year. 

Maybe it supports SVG out of the box? Reports say it supports downloaded media such as MP3 which is interesting, and has a plug-in architecture so Flash (Flash Lite most likely) can't be far off. Another reason to dust off those Flash 4 manuals I think...