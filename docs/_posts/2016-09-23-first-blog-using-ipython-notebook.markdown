---
layout: post
title: "My First Blog Post Using an IPython Notebook"
date: 2016-09-23
---

This is it — my first post written entirely as an IPython notebook and published through Nikola. The workflow is:

1. Write a notebook with text and code cells
2. Nikola converts it to HTML
3. Deploy to GitHub Pages

To get this working, I followed the guides from [Damian Avila](http://www.damian.oquanta.info/posts/ipython-plugin-for-nikola-updated.html) and [Shankar](https://shankarmsy.github.io/posts/blogging-with-the-awesome-nikola-ipython-and-github.html).

Here's what the notebook looks like — just some basic Python to prove it works:

```python
import sys
print('Python: {}'.format(sys.version))
print('This is really exciting')
print('hello, notebook blog :)')
```

It's not much, but seeing code render cleanly on a blog I control feels great. The barrier between "I wrote some code" and "I shared what I learned" just got a lot lower.
