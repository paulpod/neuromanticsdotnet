---
title: Year note 2022
date: 2022-12-19 11:55:00
tags: work
---
It is New Years Day and I'm writing this as a work marker for the year just gone. It's been a long year, for me. A bit of a slog. What got done?

## NHS 111 - Location

I'd been itching to sort out this for ages, we'd get at least one user feedback a day about people not being able to access the 111 online service with their totally valid postcode. It was usually in Wales, or Scotland and sometimes in a new build property with a brand new postcode. Yes there's a geolocate function, but it doesn't always work for people *because of reasons*.

[![Deep dive too far](/images/postcode-levels.png)](/images/postcode-levels.png) 

This turned into a deep dive into place finding, the structure of postcodes and thinking about ways to let people tell us where they are.

[![How we can use the postcode to direct people to the right service for the country they are in](/images/111-regions.png)](/images/111-regions.png) 

So we fixed that with a quick check on the postcode country, and if it was in Wales we'd say so and direct them to the Wales 111 service. Same for Scotland and Northern Ireland. Where the postcode didn't make sense, we'd nudge them to double check it - if it's not your own, it's easy to swap a number and letter by mistake. 

[![Using the Google Places API for people to tell us where they are if a postcode is not available](/images/placefinder.png)](/images/placefinder.png) 

And if it's just not working or you *don't even have a postcode* we've got a whole separate placefinder lined up that uses the Google Places API to search for places like canals, public spaces, landmarks and buildings. Looking forward to seeing that go live in 2023.

## NHS 111 - Sex and gender

The big one this year, working with the research team to find a better way to ask for a users sex. Our triage is mostly binary male/female and beyond our scope to unpick that. But we know asking upfront is an issue, hence the pretty long explanation text on the existing question.


[![A snapshot of how we currently ask about sex](/images/sex-asis.png)](/images/sex-asis.png) 


What would be a more inclusive way to ask this question? Let's find out - and the most in depth user research programme I've been involved with started. We took roughly 6 rounds of designs to a wide range of over 50 users - female, male, non-binary, trans men, trans women, intersex and people with a difference in sex development. 

We tried quite a few design approaches, at first trying to simpler solutions where pregnancy was involved with the triage routes, and we did reduce the number of symptom routes down where many of them were clearly single sex or unisex.


[![A snapshot of just some of the variations we have explored for asking a user their sex](/images/sex-questions.png)](/images/sex-questions.png) 

To do that though we had moved the sequence of the 111 online triage to get the user to choose their symptom first, but that then allows us to ask about sex only when needed, and to ask about what body parts are relevant to the symptom and the questions in the triage ahead. 

The exact wording of the questions and supporting text have been through even more revisions than that - at least 20, as we get to a solution that fulfils the needs of clinical triage while allowing as many people as possible to go on and complete an online triage without being excluded. 


[![Where we got to with asking a users sex, where relevant, and clarifying body parts ahead of a specific triage pathway](/images/sex-screens.png)](/images/sex-screens.png) 

We've been keeping our heads down with this work, due to ongoing culture war all around, but we think we've got a good place with it. More technical and clinical work remains to put this live, but hopefully it should emerge later in 2023.

## NHS 111 - Opening times

What should have been a *tiny workaround* for where a service is open across midnight and closes the next day turned into a mind bending journey.

Finding real edge cases of opening times, closing times, lunch times, bank holidays, one-offs and understanding how *most* people call things has been super fun. A set of rules around how we tell people opening times, when to tell people about imminent closing and opening times has emerged. It's not as simple as I would have liked. That's time in the real world for you. There's a whole ISO standard for it.

## Sway Democracy

On the side, the little startup idea I'd been involved with since 2016 has gone through many transformations. It currently sits as a working beta, as a browser plugin that can analyse a users social media feed and layer on additional context for news story links.


[![Sway as was - news story reader, voting, weighting of votes on how well-read a user was, etc](/images/sway-action.png)](/images/sway-action.png) 

Where a news source is generally unreliable, it will flag that. Where a story from a generally reliable source is poor, it can highlight that. It will also signal the where on the political spectrum a news source, author or story fits.

[![Sway as is - enhancing the user timeline on social media with truthiness and political bias meters](/images/sway-tweet-and-desktop.jpg)](/images/sway-tweet-and-desktop.jpg) 

We got it built! It's working, in private but I'm unsure where it goes from here, and will probably be stepping away from Sway this year. I think my ideas and energy for it is exhausted at this point. I think I need a side project that is just more fun and invigorates - not a depressing reminder of the infowars we are trapped in. 


