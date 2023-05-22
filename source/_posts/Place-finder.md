---
title: Place finder
date: 2023-04-05 09:45:16
tags: work
---
I wrote a little bit about this previously https://neuromantics.net/2022/12/31/year-note-2022/ in the 2022 yearnote and the older search for NHSD https://neuromantics.net/2019/02/16/search-for-nhs-digital/

This little tool has been bouncing around prototypes of mine for a long time. It uses the Google places API to look up actual place names. It works with postcodes of course, as well as towns, villages, road names and shops. 

"But everyone has geolocate, Paul, why would you need this?"

Well, they do except when it doesn't work. The device might be on a wifi or wired connection, where the guessed location from the network is mildly or even wildly wrong. We've seen devices that are locked down by corporate IT where permissions are set to block many functions - including location.

"But everyone knows their postcode, Paul, why would you need this?"

Except when they are out and about, like our patient having a suspected heart attack at the shops or our paramedic out on calls.

Sometimes you just need to say, "I'm near the Lidl in Bristol, no not that one, this one" and for our initial location that is accurate enough to provide the right results.

It's live now in the main 111 online service, expertly implemented with an accessible autocomplete adapted from GOV.UK. It's a bit spendy, and while the vast majority of people do use postcode or are successful with geolocate, it appears as an alternative to try on the error page for those main routes. 