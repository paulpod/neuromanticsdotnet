---
title: Braindump on Mastodon
date: 2023-07-30 11:31:28
tags: 
---
Mastodon remains problematic, can we fix it?
===
[![Arrrrgh](/images/here-we-go.jpg)](/images/here-we-go.jpg) 

A designer thinks out loud
==
All this is super opinionated. 

However, it is informed by the *great* user research Erin Kissane has done with mastodon users who were on bluesky. 500 responses is solid.

Start here https://erinkissane.com/mastodon-is-easy-and-fun-except-when-it-isnt

(We make decisions in my day job on prototype features that have been in front of a couple of rounds of 6 or 7 people. So yeah, this is solid enough for an opinionated designer to have a go.)

Design features
==

I say “design” in the loosest sense, as some of this is technical (implementation) or technical (design choice) or design (user behaviour/interface/presentation).

*Users:* “got yelled at, felt bad”
=

This on the network norms on their side is very telling. The network is the people, not just the people who were there first. If your network requires behaviour police it’s not as 

*Issue:* Content warnings
==

The content warning stuff. I mean obviously this isn’t going to scale. People are not going to do the work to think and classify and do it for even triggering subject matter let alone pictures of bugs. Get real.

*idea: stick it in in the client*
We have at our futuristic fingertips new tech (ML/AI obvs) that is pretty good at recognising the subject in an image or bunch of text. If you need CWs on everything / some stuff you should be able to get that tailored for you in a standard way in a client.

*idea: handle it on the instance*
Where a particular instance has a certain preferred behaviour, probably the onus is on the community that has that need to host the computation and moderation needs to implement. Probably? 

*idea: process it at posting*
Could be “client”, could include it in the server. Process it as a post is published. Guess, ask, suggest, cajole, mark up with some metadata and the onward instances or clients and users can handle it as they see fit.

*Users:* couldn’t find people or interests, people didn’t stay
==
It turns out those “people” algorithmic inserts are fantastic, who knew?
￼
[![People finder algrithmic units](/images/people-finder-units.jpg)](/images/people-finder-units.jpg) 
￼
*OK - Why can’t any of the clients do this?* 
I’m assuming it looks at your existing friends, graphs the overlaps, picks out ones you don’t currently follow. Is that just super hard in fedispace? I don’t know.

It does feel like decisions made by a small number of people who don’t want to be found, don't care about being found. Maybe they actively dislike being surfaced by algos have been imposed on everyone. That feels like it is having anti-network effects.

But aside from clear discovery features, the other users in a conversation 	need to be more present, to see and maybe follow them. The visibility of usernames in replies is a simple fix.

Twitter example: here a retweet shows the user doing the retweeting, the user who posted the reply, the users they are replying to and an account name in the reply content. There‘s a dense package of potential connections here.

[![People-rich content units](/images/rich-people-linking-tweet.png)](/images/rich-people-linking-tweet.png) 

As Kissane says, Mastodon has much to learn from “more conversationally fluent networks”.  When you can’t even follow the flow of a conversation, it’s difficult to engage and enjoy. There is no flow, only posts. Half the time the replies to any given post don’t load, or some are missing. Kills any flow.

As for finding content, regular Mastodon *search* isn't so bad but who wants to type things. Cross referenced discovery, from boosts and faves follows a similar pattern to users. Surely clients could do this more? Currently none of them do, as far as I am aware.

Example below - Instagram vs Mastodon search:

[![Of course the mastodon one adds a graph for nerd reasons](/images/kittens-search.png)](/images/kittens-search.png) 

Mastodon is anti-fun
=
Is fun 500 characters? It is not. I’m not reading all that. 

Opinion here, but if replies functioned more reliably a limit of half that might aid flow of conversation? Replies can flow from each of the smaller units. Is that good or bad? Seems less serious, more throwaway ... more fun?

Are threads disliked on Mastodon? Seen as engagement thirsty, an artifact from the commercial sites? It is not clear to me.

Mastodon does seem founded on some defaults and structures that are anti-network and anti-social(software).

These defaults could be pushed back on, but how to do without alienating the earliest prickly users, I don’t know. 

Unlike the web, does Mastodon even want to think this is for everyone?

---

I’m out of steam on this Sunday morning, so will post and revisit. It’s a whole thing, huh?

I had hoped to draw some things but, words eh. Not even really had time to digest the quote tweet / pile-on / moderation issues. It’s definitely a whole thing - a *job* probably.
