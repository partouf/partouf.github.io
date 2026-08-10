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

### Pronouns — hard rule

**"I", "me", "my", "mine" always mean me, the human author.** Everywhere: post
bodies, disclaimers, footnotes, captions, commit messages in the published
sense. No exceptions.

The LLM is always third person — "an LLM", "it". Never write the LLM as "I".
Never write a sentence where the reader has to work out which of us is
speaking.

**"We" means me and the reader**, which is an established habit in my writing
("we can rewrite this code in a lot of ways", "why did we do this again?").
Do not repurpose it to mean me-and-the-LLM. If a sentence needs to describe
joint work with the LLM, name it explicitly: "I asked it to...", "it turned
up...", not "we found".

This rule covers the post body. `assisted_note` is deliberately outside it and
is written as third-person credits instead — see [Disclosure](#disclosure). The
underlying point is the same either way: a disclaimer the reader can't parse
attribution from is worse than none.

Things I'd rather you did:

- Tell me when an argument doesn't hold up. That's more useful than prose.
- Ask before inventing technical specifics — benchmark numbers, version
  history, who-said-what. Getting a compiler detail wrong is worse than
  leaving a gap.
- Keep code examples compilable and actually tested where that's possible.

## Voice

Derived from ~98 posts across the old WordPress blogs (twigleaf's crossed
wires 2008–2017, twigbits 2013–2018, melodyeverywhere, saikomud). This is
descriptive, not aspirational — it's how I actually wrote, not how a style
guide says to write.

### Openings

Drop straight into the situation, first person, concrete. No thesis statement,
no framing paragraph.

> "For the last few months (no not 24/7) I've been working on a multiplatform
> library in C++."

> "I was watching a video about a mathematical concept in which someone tried
> to explain..."

> "I always get cranky when reading discussions about Threads."

Never open by restating the title, and never announce what the post will cover.

### The second-person walkthrough

The most distinctive habit: narrate the reader through an experience as though
it's shared and inevitable. Not "one might find" — "you'll come across".

> "So you look at the available options of libraries to use, and you'll browse
> the websites of the 2 major players around."

> "The thing that will eventually make you hit a large wall of nastyness, is..."

### Sentences

Long, clause-stacked, comma-spliced. Qualifiers and hedges stay — "somehow",
"generally", "pretty much", "I suppose", "sort of", "actually", "really".
Parenthetical asides mid-sentence, often the funniest part:

> "(seriously, the person who made up that network-byte-order-mechanism was insane)"

> "(did I mention how obvious these examples are?)"

Do NOT compress this into clipped declaratives. Short punchy sentences are a
different writer.

### Endings

Technical posts deflate rather than conclude. Self-deprecating shrug, then out:

> "Anyway, I'm not sure what my point was... Oh right."

> "I really thought I had something interesting to talk about when I started
> this post... I guess not..."

> "Anyway, enough ranting. Time to upload it to subversion."

> "But why do it the easy way when we can apply really slow and impractical
> concepts from functional languages ;-)"

Never end with a paragraph that summarises the post back to the reader.

### Explaining technical things

- Show the naive version, then improve it in visible steps. Real code, inline.
- Measure and state actual numbers: "This program takes 14 seconds to run on my
  machine". "runs now in 6 seconds instead of that initial 14".
- Drop to assembly/opcodes when that's where the answer lives.
- Explain from first principles — "multiplication is just another fancy word
  [for] adding the same number to your result for a number of times".
- Admit the limits, including when the compiler wins: "the compiler cheats and
  speeds it up to 2 seconds".
- Languages are whatever fits: Delphi/Object Pascal, C++, C#, PHP, JS. Not a
  purist about any of them, and openly skeptical of STL/Boost orthodoxy.

### Register

- Exasperated but affectionate about technology. Rants land on acceptance
  rather than outrage: "But the language is there ... so we have to accept
  that and move on."
- Comfortable saying "I don't know" and "I got this working and I'm not sure
  why". That honesty is a feature — keep it.
- Mild profanity in passing ("googled my ass off", "the damn thing"). Fine, not
  forced.
- Emphasis by capitalising a word mid-sentence: "Actually rewriting", "I do Not
  feel straight". Keep this — it's a tic, but it's the right tic.
- Emoji are rare and load-bearing. Only when an actual emotion needs conveying
  and the words alone won't carry it — never as decoration, punctuation, or
  tone-softening. Default to none.
- The frequent `;-)` in the old posts is period texture, not a current habit.
  Don't sprinkle emoticons in to sound like 2010.

### Later-period structure (2015+)

Newer posts are more organised than the 2008 ones: short section headings,
often phrased as questions — "Why are global states bad?", "And does it
actually work?", "Why did we do this again?" — plus bulleted takeaways at the
end. Prefer this shape for anything substantial.

### The personal-essay register

twigbits posts (identity, ethics, people) are a different mode: warmer, slower,
extended metaphor, and they DO land on a real point rather than a shrug.
Direct and unguarded without being dramatic. If a post is about people rather
than machines, switch to this register.

### Open question: how much to clean up

<!-- TODO(partouf): decide this one. -->

The old posts are knowingly unproofread ("post is not grammar/spell-checked.
not going to either, forgive me") and carry consistent non-native-English
patterns — dropped articles, "nastyness"/"readyness", "etcetera" spelled out,
occasional agreement slips. Unclear whether that's texture worth keeping or
friction worth removing. Until decided: fix outright typos and grammar errors,
leave sentence rhythm and word choice alone.

### Still banned

- "In today's fast-paced world", "Let's dive in", "It's worth noting that"
- Listicles as the whole structure ("N things you should know")
- Emoji in headings
- LinkedIn-voice: short punchy fragments. For emphasis. Like this.

## Disclosure

Every LLM-assisted post is prefaced and summarised. Two frontmatter fields:

```toml
assisted = true
assisted_note = """
I set it off to dig through the build logs for the actual numbers, which
turned up two things I had wrong. The argument and the mistakes are mine.
"""
```

`assisted = true` renders *"Written with LLM assistance. Details at end."* in
italics under the post metadata, linking to a **Disclaimer** section rendered
after the post body from `assisted_note`.

Set `assisted` honestly and err toward marking it. Substantive editing counts,
not just drafting.

**`assisted_note` must be specific to that post.** Say what was actually
delegated — what I asked it to dig up, what it drafted, what it got wrong, what
stayed mine. "This post was written with AI" tells the reader nothing and is
worse than no disclosure, because it looks like a compliance checkbox. If a
post's note would be interchangeable with another post's note, it's not
finished.

The note itself is credits, not prose — third person, naming both parties:

```toml
assisted_note = """
Concept by Partouf. First drafts by Claude, three of them, each too long.
Cutting and final text by Partouf. The closing line is Claude's, kept as-is.
"""
```

The pronoun rule above governs the **post body**. The note is the one place
that steps outside it, because credits are unambiguous about who did what in a
way "I" and "it" have to work at. Name me as Partouf and the LLM as Claude (or
whichever model it was) — don't fall back to "we" or to an unattributed passive
("was drafted with AI help"), which loses exactly the information the note
exists to carry.

Mechanics live in `layouts/_partials/post_meta.html` (preface) and
`extend_post_content.html` (disclaimer), styled by
`assets/css/extended/assisted.css`. The preface is guarded by `eq page .` so it
does not leak into list views — keep that guard if you touch it.

## Publishing

Never push to `main` without me asking. Drafts and local commits are fine.
