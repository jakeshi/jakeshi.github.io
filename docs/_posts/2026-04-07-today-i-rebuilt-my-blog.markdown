---
layout: post
title: "Today I Rebuilt My Blog (Human-Revised)"
date: 2026-04-10 00:00:00 -0700
categories: general update
author: Jake
---

Today, I rebuilt my blog from the ground up, and I had an AI pair programmer for the entire ride. This wasn't about letting the AI write for me; it was about directing a very fast, very capable intern. My job was to provide the taste and direction; the AI's job was to do the grunt work.

The first problem was untangling years of git history. I had a dozen stale branches, half-finished ideas, and a `gh-pages` branch that was a mix of old and new. I told the AI to treat `gh-pages` as the source of truth and surgically merge the good stuff from other branches without breaking the live site. Within 15 minutes, we had a clean, linear history.

Next, we tackled the content itself. Old posts were a mess of raw HTML and broken links. I gave the AI a simple command: "Convert all these posts to clean Markdown, fix the navigation, and preserve the original content." It was a tedious, manual job that would have taken me hours. The AI did it in ten minutes.

Then came the local development environment. I hadn't touched this blog in a while, and my Ruby setup was a mess. Instead of debugging gem conflicts myself, I just described the errors to the AI. It diagnosed the problem, gave me the exact commands to run, and got my Jekyll server running. No more guessing and pushing to see if things worked.

With a working local setup, I could finally focus on the design. I wanted a cleaner, more editorial look. I gave the AI high-level feedback: "make the navigation simpler," "use a stronger font," "clean up the post stream." It would generate a new version, I'd say "closer, but make the header bigger," and it would iterate. We went through five revisions in 20 minutes.

Finally, we updated the small stuff: blog title, intro copy, contact info.

The big takeaway here isn't that AI can build a blog. It's that AI is a powerful force multiplier for a human with clear intent. I knew what I wanted, and the AI was the tireless intern that executed my vision. It turned a weekend project into a two-hour sprint.

A lot of the advice out there about AI writing is garbage. It treats the AI like a magic box that spits out perfect prose. It's not. It's a tool, and like any tool, it requires skill to use well. The goal isn't to get the AI to write *for* you; it's to get it to write *with* you. It's a dialogue, not a monologue. If you're just taking the first output, you're not creating, you're just curating. And curating isn't enough.

This is the future of creative work. Not AI replacing us, but AI augmenting us. The human provides the taste, the judgment, the "why." The AI provides the "how."

Steal this workflow. Make it yours.
