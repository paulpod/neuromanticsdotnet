---
title: Enabling CarPlay on an Audi TT (8S)
date: 2024-04-18 21:22:23
tags:
  - carplay
  - technology
categories:
  - technology
---
Way, way back in time (2014) I bought a 2007 Audi TT (8J). Fun car, SHIT stereo and satnav. It came with the standard (at the time) RNS-E, which I absolutely hated, and DIY replaced very quickly with a (then brand new) CarPlay capable unit from Pioneer. I [wrote more about that](https://neuromantics.net/2015/02/26/six-months-with-carplay/) at the time. 

![RNS-E unit](/images/audi-rnse.jpg)

Good things don't last forever, and new cars become old cars. But it was a fun car, so I replaced it with an identical newer version - a 2019 TT (8S). Lots of fancy modern tech, awesome.

But wait a minute, someone seriously bought a new car in 2019 without CarPlay? And never got it added? Amazing. OK how hard could that be, huh? It turns out, brilliant naughty people have been doing this for a while and here are my notes on how I did it, in case I need to do it again.

![Success part one](/images/greenmenu-success.jpg)

1. One, full sized, not vast SD card. I reused an old Transcend 4GB that was in a Raspberry Pi. 
2. Don't use a Mac (ok, I did, but in legit Intel Bootcamp Windows)
3. Download the source code ZIP file from [the github repo](https://github.com/Mr-MIBonk/M.I.B._More-Incredible-Bash/releases/tag/V3.6.0)
4. Download the patched firmware from here  https://mibsolution.one/#/1 u: guest / p: guest - you only need the one for your vehicle/firmware combination
5. Unzip and put on the SD, put the patch in the Patches directory
6. Change the autorun filename so it autoruns
7. Put in car SD slot, start car, let it do it's thing with about 3 reboots. Maybe 5 minutes or so
8. When it's stopped doing that, access the green dev menu
9. Run the new tool, use the All In One (AIO) patch to change the firmware on your brand new car. Eek. Wait a while ... 5 mins or more. You can scroll down to see console log messages to tell you when it is done
10. Run the FEC _Add FEC container_ command just below it, to change the allowed options previous owners hadn't paid for. Wait a while ... 2 mins or so
11. Exit, reboot the entertainment unit.
12. Connect with a *good* USB/Lightning cable
13. Very carefully say yes to the UX messages from the car, your phone, more from the car, etc
14. You have CarPlay. Do a success dance

![Success part two](/images/carplay-success.jpg)

Remove SD card, go for a nice drive.

Notes:

1. I believe the factory RNS-E can now be upgraded to have CarPlay https://www.navinc.nl/20195672
2. I might be a bit harsh on the RNS-E, as newer firmwares seem to available from an enthusiast https://rnse.pcbbc.co.uk
3. Car button combos to get to the red menu (to look up your current firmware version) and green menu (to run the downloaded tool) and reboot the unit https://github.com/Mr-MIBonk/M.I.B._More-Incredible-Bash/wiki/%22hidden-menus%22---key-combinations
