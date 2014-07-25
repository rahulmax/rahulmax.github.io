---
layout: post
title:  "Google Play Store totally ignores accessibility"
date:   2009-01-01 00:00:00
categories: experiments
excerpt: <p class="postdesc"></p>
---

<img src="/images/googleplay/main.png" alt="" style="">

Refer screenshot above. Can you read the text inside the green button on the right? I can. But not without straining my eyes. But wait, it gets worse from here — This is what happens when you hover over the text.

<img src="/images/googleplay/mainhover.png" alt="" style="">

Having worked with lots of Government clients and ensuring accessibility for all of them, I usually don't make a mistake gauging the contrast between foreground and background colors, just by looking at them. Here, the contrast ratio seemed alarmingly low.

Google Play's buttons have white text against the color `#B3C833`, a similar green as the android logo. On hover, it changes to white text against `#C1D739` which makes it worse.

Nevertheless, I ran a contrast check with WebAIM's contrast checker and it failed! Miserably! It has a contrast ratio of 1.87:1 which is pretty unreadable.

<img src="/images/googleplay/webaim.png" alt="" style="">
<blockquote>
  <p>"level AA requires a contrast ratio of 4.5:1 for normal text and 3:1 for large text. Level AAA requires a contrast ratio of 7:1 for normal text and 4.5:1 for large text." — From WCAG 2.0</p>
</blockquote>

If they had used a darker color like `#60752a` it would still look better and will be accessible for every one.

<img src="/images/googleplay/proposed.png" alt="" style="">


None of the other button/text colors pass accessibility checks either, but the green color, theme for the app section is the worst.

`#1AA1E1` on white — FAIL

`#CE5043` on white — FAIL

Buttons

`#FFF` on `#B3C833` — FAIL

`#FFF` on `#1BB5FF` — FAIL

`#FFF` on `#E45A4E` — FAIL

It's been like this since years now. Hopefully Google Play Store might fix it one day!