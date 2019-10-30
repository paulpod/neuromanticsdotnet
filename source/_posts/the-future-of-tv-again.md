---
title: The Future of TV (again)
url: 174.html
id: 174
categories:
  - technology
date: 2009-05-08 14:36:15
tags:
---

Now, far be it from me to dare rerun the entire 10 years of my life, but let's just say I've fiddled with a lot of possibilities for "the future" of TV, including attempting a web2.0 startup around that whole gig. Seen and done quite a bit, nothing has quite hit the home run yet. 

This makes me pretty picky when it comes to what I use myself to watch TV on, so it'll come as no surprise that I was a UK TiVo user (one of the few) for years, supplemented by a Phillips Streamium for content, _er, acquired_ from elsewhere. 

We didn't get TiVo upgrades, so it eventually withered on the vine a bit, I had cable and a V+ PVR box for a while with an Xbox360 replacing the struggling Streamium and while quality was good, UI was worse than earlier days. 

Now I'm back on the Freeview set of channels (fine by me, didn't watch much OwlTV to be honest) and immediately felt the pang of missing PVR so bought a Topfield (Toppy) for the tinkering potential. A good job it can be tinkered with too as the UI is not good to start with and the user community improvement MyStuff is better in some ways (++ functionality, capability) and worse in others. 

The main problem is shoehorning a load more functions into the existing, already very poor remote control. So, let's network it, stick a bespoke web interface between me and the mess and use an iPod touch and iPhone as über-remotes. Here is a bunch of notes, steps and links to make this project happen. 

**1\. Set up a convenient network for the Toppy** The Toppy has USB, but only has the connectivity of a dumb storage device so needs a smart box to sit beside it. I bought a Linksys NSLU2 (the Slug) off ebay for £50, and extended my existing wifi network (ZoomADSL box handling DCHP wired to a Time Capsule handling wireless) using an old Airport Express as a WDS remote. T

his was not easy, but these articles helped: [Apple Support Doc : Using The Airport Express on WDS networks](http://support.apple.com/kb/HT2044) [O'Reilly.com : Taming an Airport Express WDS network](http://broadcast.oreilly.com/2009/03/taming-an-airport-express-wds.html) 

But after getting the WDS network to actually work, speed was very poor. Setting the Airport Express to _not_ allow wireless clients resolved this ...eventually. 

**2\. Hacking the Slug** The Slug needs a hacked firmware to turn it into a very small, quiet web/ftp server. 

One roadblock on the official route ([http://www.nslu2-linux.org](http://www.nslu2-linux.org)) \- firmware uploading Mac OSX software Upslug2 is only available as a PPC binary, but "here's the source, here's macports.org, go compile your own" - oh, please just give me it already. 

([Thank you Paul O'Brien](http://www.paulobrien.net/flashing-your-nslu2-via-a-mac-upslug2-binary/) for saving a whole bunch of people a whole bunch of time and bandwidth.) Next up, I seemed to have trouble getting the only USB flash drive (512MB) I had to hand formatting correctly on the Slug, so tried a new, larger (4GB) one which formatted as ext3. 

I'll also try recycling another old bit of kit by adding a USB SATA enclosure for the Macbook drive I upsized a few months ago. The rest of the instructions for Unslung and unslinging the new OS onto the flash drive are very clear and straightforward. 

**3\. Connecting to the Unslung Slug** Using a browser to the web GUI of the Slug worked fine, couple of gotchas: - telnet needs to be reactivated each time the Slug gets rebooted - turn off the built in FTP server on the Slug from the web GUI - install ftpd-topfield as documented - connecting using Transmit worked fine 

**4\. Installing MWI (MyStuff Web Interface)** Following the instructions I installed all the packages. I didn't quite understand when it came to configuring the mysql install, getting errors instead of running - this was solved by typing the m in rather than copy & paste, so assume it was a line ending or stray character error. 

Anyway, copying the text in BBedit for the mysql setup worked too. The rest of the config was easily done in vi. Next issue was getting the files across - sftp needs adding (which I had assumed was added with openssh, but no)

ipkg install openssh-sftp-server

You will also need to change the /dev/null permissions, otherwise you will get an SFTP connection error:

 chmod 777 /dev/null