---
title: MX 2004 Upgrade or Migration Problems & Fix
url: 123.html
id: 123
comments: false
categories:
  - technology
date: 2006-07-16 09:05:58
tags:
---

Just a note to myself and anyone else that gets stuck upgrading OSX, or migrates to a new mac and suddenly finds Director MX 2004 and Flash MX 2004 now failing to start up correctly, characterised by a bouncing icon but never getting to splash screen, requiring a force quit. This worked for me: run the macromedia hotfix for this issue, repair permissions using disk utility, run hotfix again, open the apps - the 30 day trial will be reset, and you can enter serial numbers at your leisure. I believe the real issue is the hidden files Macromedia used to protect the software and manage the 30 day trial got messed up - the hotfix deletes a Macrovision directory and files related to this, so deleting that manually may have a similar effect. That little pain in the arse took the shine off an otherwise seamless migration to a new MacBook Pro replacing a tired, battered and well used 1Ghz TiBook. Old laptop will go to a deserving retirement home, the new one is very shiny and very quick - easily the speed of my 2x2Ghz G5 tower. Nice.