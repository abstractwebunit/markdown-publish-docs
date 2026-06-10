# FAQ

## The site opens but looks "bare": no styles, notes don't load, 404s in the console

This is almost always `baseHref`. On GitHub Pages the site lives under the sub-path `/your-repo-name/`, and the build needs to know about it:

- in the workflow: `base-href: /your-repo-name/` (see [[GitHub Pages]]);
- on Netlify/Vercel/Cloudflare the site lives at the root — leave it as `/`.

## I deployed changes, but the site shows the old version

Browsers cache static files tenaciously. Press **Ctrl+Shift+R** (hard reload) or open the site in an incognito window. This especially applies to [[Canvas Boards|canvas boards]] — they're loaded as a separate file.

## How do I hide some of my notes?

`buildMode: public` in [[Configuration]] — only notes with `publish: public` in the frontmatter get published. The rest don't make it into the build, the search, or the graph.

## Are Cyrillic file names okay?

Yes. Page URLs keep non-Latin characters such as Cyrillic, just like Obsidian Publish. The Russian version of this site is a live example.

## Which links between notes are understood?

Both `[[wikilinks]]` (with `|aliases` and `#headings`) and regular `[text](another-note.md)` links. Both kinds end up in the [[Link Graph|graph]] and in backlinks.

## Images and attachments?

Put them next to your notes and embed them as usual: `![[image.png]]` or `![alt](image.png)`. During the build the files get hashed names and end up on the site.

## How much does it cost?

markdown-publish itself is free and open source (MIT). GitHub Pages, Netlify, Vercel, and Cloudflare Pages all have free tiers that cover personal notes with plenty of room to spare.

## Is this an official Obsidian product?

No. The project is not affiliated with Obsidian.MD — it simply reads the compatible format of vaults and `.canvas` files (the open JSON Canvas standard).

Didn't find your answer — [ask a question in the issues](https://github.com/abstractwebunit/markdown-publish/issues).
