---
layout: post
title:  "today I rebuilt my blog"
date:   2026-04-07 21:30:00 -0700
categories: general update
author: Jake
---

Today was a full reset and cleanup day for my site.

I started by cleaning up git branches and confirming what was active vs old history.
Then I merged obsolete branch history safely, without overwriting the current `gh-pages` content.

After that, I migrated older posts from legacy branches into the current Jekyll blog, cleaned broken legacy navigation bits, and converted imported HTML posts into cleaner Markdown.

I also set up a newer local Ruby runtime so the site could render properly on my machine.
That helped me actually preview and iterate on the real `gh-pages` source locally.

Then I redesigned the homepage and overall style to feel closer to the editorial style I wanted:

- simpler navigation
- stronger typography
- cleaner post stream
- less visual noise

Finally, I updated site identity details:

- blog title to **Jake Shi**
- homepage intro copy
- contact email link to **jakexshi@gmail.com**

Big takeaway from today: progress compounds fast when you clean structure first, then design.
