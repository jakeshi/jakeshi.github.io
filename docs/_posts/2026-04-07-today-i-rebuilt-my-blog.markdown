---
layout: post
title:  "today I rebuilt my blog"
date:   2026-04-07 00:00:00 -0700
categories: general update
author: Jake
---

Today was a full reset and cleanup day for my site.

I used AI as a pair engineer for the whole process.

I started by asking AI to inspect my git branches and separate active history from obsolete history.
Then we merged old branch history safely, without overwriting the current `gh-pages` content.

After that, AI helped migrate older posts from legacy branches into the current Jekyll blog, clean broken legacy navigation bits, and convert imported HTML posts into cleaner Markdown.

I also used AI to troubleshoot local runtime issues and set up a newer Ruby environment so Jekyll could render properly on my machine.
That made it possible to preview and iterate on the real `gh-pages` source locally, instead of guessing.

Then AI helped me redesign the homepage and overall style to get closer to the editorial look I wanted:

- simpler navigation
- stronger typography
- cleaner post stream
- less visual noise

I iterated quickly by giving AI direct feedback like “closer,” then applying another pass.

Finally, I updated site identity details:

- blog title to **Jake Shi**
- homepage intro copy
- contact email link to **jakexshi@gmail.com**

Big takeaway from today: AI works best when I drive intent and taste, and let it handle the repetitive heavy lifting.
