---
title: Search for NHS Digital
date: 2019-02-16 14:24:39
tags:
---
I was in a conversation with the wider NHS Digital design team yesterday, providing some pointers for people starting search-related projects. It was good to summarise some of the things we've learned building Service Finder v2, and it was suggested I write it up.

Special snowflake
====
Our search tool has _unconventional requirements_ so let's run through those first. It is a structured search query with a number of parameters expected by the backend:
* service type(s)
* location, distance/range to consider
* urgency of treatment
* patient age, sex and their GP

Within the steps to contruct this query, we have search tools for which service type(s) and finding a patients GP. We also have a location search function, that might need to work with places not just postcodes. So that's a few questions and three searches to construct a search query, and it needs all of that to function on a mobile interface.
	
The old version did all of that on one (complicated) page, but unsurprisingly there were usability issues. These issues meant the tool had poor adoption by the intended users. Meanwhile, the need for a tool like this for a much wider range of users has been identified, so we've had another go. 

Our main approach has been to break it into smaller steps, but more of them. Then, we've been able to address each of the required parameters in isolation, asking the question in the best way. With additional technical work, we've been able to reduce the need for all of the parameters.



Service types
====
There are lots of services, each belongs to at least one service type. Service types are categories like:

* District Nurse
* Palliative Care
* Cancer Care

Not all the names are quite so immediately clear, like 

* Multi-Disciplinary Service, or even
* Minor Injury Unit (MIU)

The list is too long to display, so we use an autocomplete search box. Only 1 character is required to get an instant feedback for what is going on, and by 3 characters you'll have a sensible number of results. We highlight where the match is, and there are multiple synonyms for many of the service types.

We have fuzzy search on this too, so if you mistype or misspell a word (minor/miner was a classic test case for us) it won't make any difference.

[![service type selection](/portfolioimg/service-list-autocompleted.png)](/portfolioimg/service-list-autocompleted.png) 

Users might search a bunch of service types at once, so each has a checkbox to allow multiple selections. 

There are a few groups of service types, where what you are looking for might be found better in one of the similar categories. So in the confirmation step after the service types, we play back your selection, and in some cases suggest related service types.

[![service type suggestions](/portfolioimg/service-type-selections.png)](/portfolioimg/service-type-selections.png) 

Naming of service types varies around the country, and an MIU in one area might offer more advanced treatment than in others (eg. has an X-ray facility). No, we're not able to search by facility, unfortunately, due to the free-text nature of the data. 

Location
===
This is a bit simpler, it's an implementation of a standard Google Places API lookup. You can type a partial postcode, UK road, village, town or city name. It's got Google smarts for typos, disambiguation, clever ordering (_nearest to you vs common vs magical_). You can even type a location name, like one of the Lidl's in Bristol. 

And for the mobile users, like paramedics, there's a button for "Near here" which uses the pretty reliable geolocation functions.

[![service location finder](/portfolioimg/service-finder-location.png)](/portfolioimg/service-finder-location.png) 

With all this magic location finding, it's a bit of a drag that we still need a full postcode to pass to the DoS, so if there isn't on for the region selected, we reverse lookup one to use. Exact location isn't really required, it's just to order services as nearest.


Patient information
===

After defining _service types_ and a _location_ it's possible that might be enough to fire off a search query, so that's what we do where possible ... eg. a Walk In Centre should accept anyone, so show me them now.

*But!* quite a few service types are dependent of GP catchement areas, or can only be referred through one. So for those, we ask first if they patient has one, and provide _another_ search to find it.

This is a simple autocomplete text box, searching surgery name and/or address keywords. The potentially large list of results is ordered by location, as we already know that, so it _should_ be easy to find.

We added the address to the keywords being indexed as the 'official name' of a GP surgery might not be what a patient uses.


Results
===

Finally (!) we get to a list of services that are available. We previously had a question for users to indicate a distance range, which resulted in sometimes zero results. The user would go back and forward to pick the 'correct' range, or just hit 60 miles - a nightmare in cities. 

We got rid of that, and just show all the results, nearest first, with pagination at the bottom of the list.

We also used to ask about the 'urgency' with a cut off on 1-2 hours being urgent, and up to 24 hours for everything else. This was actually polling the opening hours, to see if a service was open now or soon, or closed or closing soon. 

We got rid of it, and have a filter now for "all results" or "open now". Much simpler.








