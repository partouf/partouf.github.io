+++
title = 'Hello World'
date = 2026-08-10T21:00:00+02:00
draft = false
tags = ['meta']
summary = 'A placeholder post, and a short note on how this site is put together.'
assisted = true
assisted_note = """
This one is mostly scaffolding rather than writing. I asked an LLM to set up
the Hugo site, work out the GitHub Pages deployment, and read through a decade
of my old WordPress posts to reconstruct how I used to write. It drafted this
placeholder from that. The setup decisions, and anything wrong with them, are
mine.
"""
+++

This is a placeholder. Delete it, or rewrite it into something real.

## How this site works

It's [Hugo](https://gohugo.io/) generating static HTML from markdown, hosted on
GitHub Pages. There's no database, no PHP, no comment system, and nothing that
loads a third-party script. Pushing to `main` triggers a GitHub Action that
builds the site and publishes it.

Writing a new post:

```bash
hugo new content posts/my-post.md   # starts as a draft
hugo server -D                      # preview at localhost:1313
```

Flip `draft = false` in the frontmatter, commit, push. That's the whole loop.

## On the AI part

Some of what ends up here is drafted with help from an LLM, working from my
notes and arguments. Posts where that happened are marked with `assisted` in
the frontmatter. The thinking is mine; sometimes the sentences get help.
