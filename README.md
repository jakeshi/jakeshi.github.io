# Jake Shi's Personal Website

This repository contains the source for my personal website and blog.

The site is built with Jekyll, published from the `gh-pages` branch, and served at [jakeshi.github.io](https://jakeshi.github.io).

The README structure is loosely inspired by the clarity of [steipete/steipete.me](https://github.com/steipete/steipete.me?tab=readme-ov-file), but adapted for this repo's much simpler GitHub Pages + Jekyll setup.

## About

This site is a personal blog and writing space.

It currently focuses on:

- essays and personal updates
- product, systems, and AI notes
- experiments in public

## Project Structure

```text
.
├── docs/                    # Jekyll site source and generated output
│   ├── _config.yml          # Site metadata and Jekyll configuration
│   ├── _layouts/            # Custom page, post, and homepage layouts
│   ├── _posts/              # Blog posts in Markdown
│   ├── assets/              # CSS, images, and static assets
│   ├── about.markdown       # About page
│   ├── index.markdown       # Homepage entry point
│   ├── Gemfile              # Ruby dependencies for local development
│   ├── Gemfile.lock         # Bundled dependency lockfile
│   ├── CNAME                # Custom domain config if enabled
│   └── _site/               # Generated site output
├── .ruby-version            # Preferred local Ruby version
└── README.md                # This file
```

## Local Development

This repo uses Jekyll inside the `docs/` directory.

### Install dependencies

```bash
cd docs
bundle install
```

### Start the local server

```bash
cd docs
bundle exec jekyll serve
```

By default, Jekyll serves the site at:

```text
http://127.0.0.1:4000
```

### Build the site

```bash
cd docs
bundle exec jekyll build
```

## Publishing Model

This repository uses a simple branch-based workflow:

- `gh-pages` is the live source-of-truth branch for the site
- `drafts` is the holding area for unfinished posts and experiments
- `master` and `src` are legacy branches kept for historical reference

The site is published from the contents of `docs/` on `gh-pages`.

## Writing Workflow

### Publish a new post

1. Add a Markdown file under `docs/_posts/` using the Jekyll date-slug format.
2. Include front matter with `layout`, `title`, `date`, `categories`, and `author`.
3. Run the local server and review the result.
4. Commit locally.
5. Push `gh-pages` once the post is ready.

### Work on drafts

1. Switch to `drafts`.
2. Iterate on posts, pages, or structure there.
3. When a draft is ready, either cherry-pick the commit or copy specific files into `gh-pages`.

## Design Notes

The current site uses custom Jekyll layouts and a lightweight editorial style instead of sticking to the default minima presentation.

A few current design choices:

- serif-forward typography for titles
- simple navigation and post stream
- low-noise layout with custom CSS
- optional day/night theme toggle

## Deployment

GitHub Pages handles deployment once changes are pushed to the correct branch.

If local pushes stop working, check these first:

- the repo remote is using the intended URL
- GitHub Desktop is logged into the correct account
- the account has write access to `jakeshi/jakeshi.github.io`
- cached credentials have not gone stale

## Notes

A few repo-specific gotchas:

- Jekyll commands need to run from `docs/`, not the repo root.
- `_config.yml` changes require restarting the local Jekyll server.
- The generated `_site/` folder lives inside `docs/`.
- Local Ruby and Bundler versions matter; mismatches can break builds quickly.

## License

Unless otherwise noted, the writing and code in this repository remain owned by the repository author.
