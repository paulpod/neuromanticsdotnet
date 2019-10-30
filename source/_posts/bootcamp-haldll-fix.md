---
title: Bootcamp Hal.dll Fix
url: 126.html
id: 126
comments: false
categories:
  - technology
date: 2006-08-20 11:03:52
tags:
---

Partly for my own memory, and partly for what seems to be lots of people having Bootcamp problems when installing XP:

Problem: Nice clean Bootcamp partition - Check! Nice clean pukka XP SP2 disk - Check! Install and go... nuts - what is this C: \\windows\\system32\\hal.ddl corrupt or missing you speak of? Ekk! Knowing \*nothing\* about this level of windows hacking I'm off to a bad start here. Here's how i got it working on my MBP.

Fixes: Apparently some people have had luck waiting till the setup off CD lets you hit 'R' and do some repair from the command line, specifically **del C:\\boot.ini** ... **bootcfg /rebuild** ... **fixboot**

Apparently that has been know to work, but didn't work for me - this did though: Back in OSX use the Bootcamp assistant to remove then recreate the partition. Then boot off your XP install CD and when setup gets to your disk selector, delete the Bootcamp partition, and delete the 200mb partition bootcamp has also quietly made. Then create a new windows formatted partition from here and install. All should proceed well this time.

I'm not entirely sure why this works but it does and I get to play Half Life 2 now. Yay!