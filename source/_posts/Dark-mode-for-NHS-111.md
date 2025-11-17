---
title: Dark mode for NHS 111
date: 2025-11-17 11:12:51
tags: work
---
> This is a set of local notes from the ones I added to the [github issue discussing implementing a dark mode](https://github.com/nhsuk/nhsuk-service-manual-community-backlog/issues/453#issuecomment-2328681420) across the NHS design system.

We looked at Dark Mode a little while ago, here is what we found. 

_(There's a bit of conversation here, and compromise explored)_
Some users have mentioned it in feedback comments and user research for a long time. Some users were forcing dark mode on their browsers using a plugin. Using that plugin, it looks like this:

[![Images from browsers using an automated darkmode plugin](/images/darkmode-automated.png)](/images/darkmode-automated.png) 

Clearly if filled a need, but there are quite a few issues with it, so surely we could do something better.

It's important to remember that users might not choose black (if given the option) for the dark mode background, as this can introduce harsh contrast issues. Their choice might be about the screen emitting less light overall, but not about maximising contrast.

The first issue is the NHS blue on dark and/or black is a complete failure.

[![Some NHS blues with WCAG colour contrast outputs](/images/darkmode-blues.png)](/images/darkmode-blues.png)

We use the blue on text links, so that's going to be the first problem. Going all out for AAA contrast of the NHS blue is going to be a little bit nasty:

[![Issues using NHS blues vs WCAG colour contrast outputs](/images/darkmode-issues.png)](/images/darkmode-issues.png)

Bearing in mind that the human eye is more sensitive to blue light than other parts of the spectrum, this seemed reasonable. I made a mockup with a visually comparable blue (along with using darker images in dark mode!)

[![Example exploring blue + image perception on dark vs light modes](/images/darkmode-blue-perception.png)](/images/darkmode-blue-perception.png)

Following this I came up with a set of compromise colours that might work in harmony to recreate our page in dark mode while keeping the feel of it. This meant a new blue, that was perceptually close to the NHS Blue but passed at AA - **#348de0**

[![Towards a compromise blue to use](/images/darkmode-compromise.png)](/images/darkmode-compromise.png)

This also introduced the need to detect the accessibility setting for high contrast, and offer a definite high contrast option:

[![Exploring the contrast side of things](/images/darkmode-contrast.png)](/images/darkmode-contrast.png)

This can be detected in a media query using the css prefers-contrast
eg.

    @media (prefers-contrast: more) {
    .contrast-enabled-box {
        outline: 2px solid white;
      }
    }

I added a few more elements, with tweaked high-contrast versions and assembled a long page with a range of items.

[![Example mobile page with many dark mode elements](/images/darkmode-mobile-examples.png)](/images/darkmode-mobile-examples.png)

High contrast above, note the addition of borders to the boxes to really pick those out, and the much brighter green, red (pink) and blue items.

The big yellow banner was particularly problematic, so even though technically just bringing the colour across would "work" it is emitting far too much light for a dark mode.

[![Example showing the issues with the big yellow boxes](/images/darkmode-bigyellow.png)](/images/darkmode-bigyellow.png)

In summary though, due to the extensive use of webviews of parts of NHS.UK within parts of the NHS App, doing these things _just for NHS 111_ was deemed not possible. All sites or none, appears to be the blocker for an NHS dark mode.
