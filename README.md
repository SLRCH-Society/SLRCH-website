# SLRCH website

Built with Jekyll and published via GitHub Pages. Most collaborators will
only ever need to edit the `.md` files listed below — the HTML in
`_layouts/default.html` and `css/style.css` handles the design and doesn't
need to change for normal content updates.

## Editing a page

Each page is a Markdown file in the repo root (`news.md`, `awards.md`,
etc.). At the top of each file is a small front-matter block:

```yaml
---
layout: default
title: Awards
description: A one-line summary used for search engines.
eyebrow: Recognition
lede: A short sub-headline shown under the page title.
---
```

Below that, write normal Markdown — headings, paragraphs, links, lists.
A `## Heading` automatically gets the site's signature gradient bar above
it, so you don't need to add any HTML for that.

## Adding a news item

Open `news.md` and add a new `### Headline` followed by a paragraph,
anywhere in the file (newest usually goes at the top). No other file
needs to change.

## Adding a page to the menu

For a plain top-level link, add one entry to `_data/nav.yml`:

```yaml
- title: Your Page
  url: /your-page/
```

For a submenu (like "About Us" or "Archives"), use `children` instead of `url`:

```yaml
- title: About Us
  children:
    - title: About SLRCH
      url: /about/
    - title: The Board
      url: /board/
```

Either way, then create the matching `.md` file in the repo root with the
same front-matter pattern as the other pages. If you want the file's URL
to differ from its filename, add a `permalink:` line to its front matter,
e.g. `permalink: /archives/abstracts/` on a file named `archives-abstracts.md`.

## Previewing locally (optional)

If you have Ruby installed:

```
bundle install
bundle exec jekyll serve
```

Then open http://localhost:4000. Otherwise, just push to GitHub and
GitHub Pages will build it automatically within a minute or two.
