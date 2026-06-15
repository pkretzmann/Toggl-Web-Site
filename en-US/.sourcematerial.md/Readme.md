# Source material for HTML

This folder contains the **source material** for the documentation in **this language** — i.e. the raw
notes, user guides, PDFs, text files and screenshots that the finished HTML pages are built from. Each
language folder (`da-DK/`, `en-US/`, …) has its own `.sourcematerial.md/`.

## What is the material used for?

The content here is the **input** to the `/html-guide` command. When the command is run on a topic, it
reads the source material in the relevant subfolder and produces a polished, self-contained HTML page from
it. The generated HTML pages are placed in the **same language folder** (and become part of that language's
documentation portal `index.html`).

```
<language>/.sourcematerial.md/<topic>/   →   /html-guide   →   <language>/<topic>/<page>.html
   (source material)                                            (finished HTML page)
```

The styling comes from the project's `.website/styles.css` (falling back to the shared
`styles-default.css`), and the interactive behaviour (table of contents, search, copy buttons, reading
progress bar, etc.) from `script.js` in the claude4bc submodule — `/html-guide` inlines them into each
page. The source material itself should therefore **only** contain content — not styling.

## Organization

Create one subfolder per topic, e.g.:

| Folder | Topic |
|--------|-------|
| `<topic-1>/` | (short description) |
| `<topic-2>/` | (short description) |

Each topic folder can contain several file types:

- **`.md`** — the primary source (written notes / user guide in markdown)
- **`.pdf` / `.txt`** — original guides or exports for reference
- **`.png`** — screenshots of setup and fields

## How to add or update a page

1. Add or update the source material in the relevant subfolder here.
2. Run `/html-guide` on the topic to generate (or regenerate) the HTML page, and place it in the
   relevant subfolder under the **same** language folder.
3. Run `/update-website` to update the portal menu (see `.website/README.md`).
