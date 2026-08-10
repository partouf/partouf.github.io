# Working on this blog

Hugo static site, PaperMod theme, deployed to GitHub Pages on push to `main`.

## Layout

- `content/posts/` — all posts. Work in progress keeps `draft = true` in its
  frontmatter (the archetype sets it); drafts are excluded from real builds and
  visible locally via `hugo server -D`.
- `hugo.toml` — site config
- `layouts/partials/extend_footer.html` — renders the `assisted` disclosure
- `.github/workflows/deploy.yml` — build + publish

## Commands

```bash
hugo new content posts/my-post.md   # new post from the archetype
hugo server -D                      # local preview incl. drafts, localhost:1313
hugo --gc --minify                  # production build into public/
```

## How to help with writing

The default mode is **I bring the thinking, you bring the drafting help**. I'll
usually arrive with bullets, a half-formed argument, or a rough draft. Expand
it, restructure it, tighten it, and push back where the reasoning is weak.

Do not write a whole post from a one-line prompt unless I explicitly ask. A post
generated from nothing reads like it was generated from nothing.

Things I'd rather you did:

- Tell me when an argument doesn't hold up. That's more useful than prose.
- Cut ruthlessly. First drafts here are always too long.
- Ask before inventing technical specifics — benchmark numbers, version
  history, who-said-what. Getting a compiler detail wrong is worse than
  leaving a gap.
- Keep code examples compilable and actually tested where that's possible.

## Voice

<!-- TODO(partouf): this section is guesswork until you correct it. Edit freely --
     the more specific it gets, the less the drafts drift. -->

- Plain, direct, technical. Assume the reader knows how a compiler works.
- Short sentences beat long ones. Cut qualifiers.
- Dry humour is fine. Enthusiasm-as-punctuation is not.
- First person, contractions, normal human register.

Banned outright:

- "In today's fast-paced world", "Let's dive in", "It's worth noting that"
- Opening a post by restating its own title as a question
- Listicles and "N things you should know"
- Concluding paragraphs that summarise what was just said
- Emoji in headings
- Em-dash pileups (one per paragraph, maximum)

## Disclosure

Posts drafted or substantially edited with AI help set `assisted = true` in the
frontmatter. Set it honestly; err toward marking it.

## Publishing

Never push to `main` without me asking. Drafts and local commits are fine.
