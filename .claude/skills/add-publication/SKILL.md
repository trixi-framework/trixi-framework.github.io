---
name: add-publication
description: Add or update a publication entry under the "## Publications" heading in index.md of the trixi-framework.github.io website. Use when the user gives a DOI and/or arXiv link (or both) for a paper that *uses* Trixi.jl / TrixiParticles.jl / TrixiAtmo.jl etc. and wants it added to the website, or wants to update an existing preprint entry with newly-published journal information.
---

# Add or update a Trixi publication entry

This skill turns a DOI/arXiv link into a correctly formatted Markdown entry in
`index.md` under `## Publications`, shows it for confirmation, then commits it to
a new branch so the user only needs to push.

## Inputs to collect

The user will give you at least one of:
- an **arXiv** link or ID (e.g. `https://arxiv.org/abs/2605.24898` or `2605.24898`)
- a **DOI** or journal link (e.g. `10.1016/j.jcp.2026.114959` or a `doi.org` URL)

Also ask for / accept (all optional):
- a **reproducibility repository** URL (the "reproduce me!" badge). This is *not*
  in any metadata — only the user has it. If they don't mention one, ask once;
  if they don't have one, omit the badge.
- whether this is a **new entry** or an **update** to an existing one.

If the request is ambiguous (e.g. only a DOI but you suspect an arXiv preprint
also exists, or unclear whether to create vs. update), ask before proceeding.

## Step 1 — Fetch metadata

Use `WebFetch` (load it via ToolSearch first if needed). Prefer these clean
sources over scraping HTML:

- **DOI** → Crossref REST API: `https://api.crossref.org/works/<DOI>`
  Returns JSON with: `author[].family` (last names, in order), `title[0]`,
  `container-title[0]` (journal), `volume`, `page` / `article-number`,
  and `published`/`issued` year.
- **arXiv** → arXiv API: `http://export.arxiv.org/api/query?id_list=<ID>`
  Returns Atom XML with author names, title, and the submission/update year.
  The arXiv ID is the part after `abs/` (strip any version suffix like `v2`).

If you have one identifier, try to discover the other: Crossref records for a
published paper sometimes omit the arXiv ID, and the arXiv entry sometimes lists
the journal DOI once published — cross-reference when possible, but never block
on it. Use whatever is available.

Extract: ordered list of author **last names only**, the **title**, the **year**,
and (if published) **journal name, volume, pages/article number**.

## Step 2 — Determine which authors are main developers

Read `developers.txt` next to this file — it is the maintained list of Trixi
main-developer last names. Wrap any author last name that matches an entry in
that list in `*asterisks*` (italics). Match on the last name exactly (accents and
hyphens included, e.g. `Rueda-Ramírez`, `Schlottke-Lakemper`). Leave all other
author names plain.

If an author looks like a developer but isn't in the list (or vice versa), flag
it to the user during confirmation rather than guessing — the list is the source
of truth and should only change when the user says so (see "Maintaining the list").

## Step 3 — Format the entry

Author last names are comma-separated, in publication order, on the first line.
Use this exact badge ordering and syntax (omit any badge whose link is missing):

Preprint (not yet in a journal):
```
* Lastname1, *DevLastname*, Lastname3,
  **Exact paper title**, <YEAR>.\\
  [![arXiv:<ID>](https://img.shields.io/badge/arXiv-<ID>-yellow)](https://arxiv.org/abs/<ID>)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](<REPO_URL>)
```

Published (has journal info + DOI):
```
* Lastname1, *DevLastname*, Lastname3,
  **Exact paper title**,
  <Journal Name> (<volume>) <pages-or-article-number>, <YEAR>.\\
  [![arXiv:<ID>](https://img.shields.io/badge/arXiv-<ID>-yellow)](https://arxiv.org/abs/<ID>)
  [![doi:<DOI>](https://zenodo.org/badge/doi/<DOI>.svg)](https://doi.org/<DOI>)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](<REPO_URL>)
```

Rules:
- Continuation lines are indented 2 spaces.
- The last non-badge line ends with `.\\` (the `\\` is a Franklin line break).
  The author line and (for published) the title line end with a trailing comma.
- **Badge order is always: arXiv, then journal DOI, then "reproduce me!".**
  (Some old entries vary — follow this canonical order for new/updated entries.)
- The arXiv badge label keeps the dot in the ID (`arXiv-2605.24898-yellow`).
- The journal-info line formatting is loose across the file; match the style of
  nearby recent entries (e.g. `Journal of Computational Physics (561) 114959, 2026.`).
- Inclusion criterion: the paper must *use* a Trixi-family package, not merely
  cite it. You can't verify this from metadata — assume the user-provided paper
  qualifies, but mention the assumption if anything looks like a pure citation.

## Step 4 — Confirm with the user

Show the fully rendered entry (and, for an update, a clear before/after diff of
the affected lines). Point out anything you inferred or are unsure about
(e.g. ambiguous developer names, missing repro link, loose journal formatting).
**Do not edit `index.md` until the user approves.**

## Step 5 — Place the entry and commit

Sections under `## Publications` are grouped by `### <YEAR>` in reverse-
chronological order; within a year, the newest additions go at the **top** of
that year's list.

- **New entry**: insert at the top of the matching `### <YEAR>` group. If that
  year heading doesn't exist yet, create it in the correct position.
- **Update** (preprint → published): find the existing entry by arXiv ID or
  title, add the journal-info line and the DOI badge, reorder badges to the
  canonical order, and move the entry to the correct year group if the
  publication year differs from where it currently sits.

Then:
1. Create a branch with a descriptive name, e.g.
   `add-publication-<firstauthor>-<year>` or
   `update-publication-<firstauthor>-<year>` (the user is on `main`).
2. Commit only the `index.md` change. Match the existing commit-message style,
   e.g. `Add <FirstAuthor et al.> (<year>)`, `add preprint <Authors> (<year>)`,
   or `<Authors> (<year>) published in <Journal>`.
3. End the commit message with the required co-author trailer.
4. **Do not push** — the user pushes to open the PR.

## Maintaining the developer list

`developers.txt` is the source of truth for which last names get italicized.
Update it (one last name per line, kept alphabetically) only when the user
explicitly says someone has joined or left the main-developer set, then commit
that change too. Don't silently add names just because they appear italicized in
a single entry.
