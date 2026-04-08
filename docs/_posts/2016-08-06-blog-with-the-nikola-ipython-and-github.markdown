---
layout: post
title: "Setting Up a Blog with Nikola, IPython, and GitHub"
date: 2016-08-06
---

I finally got a blog running. It took longer than I expected.

The setup: [Nikola](https://getnikola.com/) as the static site generator, IPython notebooks for writing posts with live code, and GitHub Pages for hosting. The idea is simple — write data science posts as notebooks, and Nikola converts them into a static site. In practice, there are a few rough edges.

## What I ran into

First, setting up the conda environment. Virtual environments didn't work for me out of the box. I ended up creating a clean one:

```bash
conda create -n blog python
source activate blog
```

Then installing Nikola and its IPython plugin inside that environment.

## Deploying to GitHub Pages

Nikola has a built-in `github_deploy` command that builds your site, commits the output to a `gh-pages` branch, and pushes it. You need to configure a few things in `conf.py`:

- `GITHUB_DEPLOY_BRANCH` — `gh-pages` for project pages, `master` for user pages
- `GITHUB_SOURCE_BRANCH` — defaults to `src`, where your source files live
- `GITHUB_COMMIT_SOURCE` — set to `True` so the source branch is automatically committed

Once that's wired up, deploying is one command. It's a nice workflow — write a notebook, run the deploy, and the post is live.

Getting here wasn't smooth, but it works. Now I just need to write things worth reading.
