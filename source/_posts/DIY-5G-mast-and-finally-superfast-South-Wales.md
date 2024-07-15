---
title: DIY 5G mast and finally superfast South Wales
date: 2024-05-27 20:26:29
tags: 
  - technology
categories:
  - technology
---

I spotted a tiny patch of 5G coverage on my phone, just the other side of the old railway bridge behind my house. Wow! 100+ whole megabits per second! Could I somehow tap that to improve the speeds at home, where we used a 4G router? Let’s find out.

Firstly, the router would need to be updated. The old one is a [Huawei 4G B535](https://amzn.to/3xZucW1) which has been fine with a Three unlimited SIM in it. These [ZTE 5G outdoor POE boxes](https://amzn.to/4fgHZsj) are widely available refurbished for around £200, some branded Three. I think they were used by Three in some installs? Anyway, that works.

Power over Ethernet is cool, so no need for a second cable, just needed [an outdoor extender](https://amzn.to/463MVMF) and a POE switch indoors - this [TP-Link 8 port gigabit POE](https://amzn.to/3XWQvGy) one was perfect. A bit of outdoor ethernet cable, and a feed through the airbrick and that was connected up. The old Huawei was fine for a wifi hub. Bosh, all connected: Speedtest says ~100 mbps. 

Add on a couple of [dumb mediaconverters](https://amzn.to/4f5BS9O) either end of the 70m fibre I had just trenched down to the cabin, another 8 port switch and we have wifi in there too at ~100mbps with another wifi box - more cheap [TP-Link kit, a POE access point](https://amzn.to/3xWD2DY) in this case. Quite happy (apart from the POE in that box not working with the same standard as POE on the switch... what?).

Finally, I mounted the 5G box on a larch pole, secured to an oak tree, just peeking out beside the road and railway bridge. You can barely see it, I hope.

![5G DIY mast](/images/diy-5g-mast.jpg)
