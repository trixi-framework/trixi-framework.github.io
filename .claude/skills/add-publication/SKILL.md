---
name: add-publication
description: Add or update a publication entry under the "## Publications" heading in index.md of the trixi-framework.github.io website. Use when the user gives a DOI and/or arXiv link (or both) for a paper that *uses* Trixi.jl / TrixiParticles.jl / TrixiAtmo.jl etc. and wants it added to the website, or wants to update an existing preprint entry with newly-published journal information. Also use when the user gives a year and wants to find journal/published versions for that year's preprint-only entries (bulk update).
---

# Add or update a Trixi publication entry

This skill turns a DOI/arXiv link into a correctly formatted Markdown entry in
`index.md` under `## Publications`, shows it for confirmation, then commits it to
a new branch so the user only needs to push.

It has two modes:

- **Single-entry mode** (Steps 1–5 below): the user gives one paper's DOI/arXiv
  link to add or update.
- **Bulk "find published versions" mode** (see the section at the end): the user
  gives a *year*; you find every preprint-only entry in that year, let them pick
  which to chase, and try to discover a journal publication for each one.

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

## Bulk mode — find published versions for a year

Trigger: the user gives a **year** (e.g. "find published versions for 2026",
"check the 2026 preprints for journal versions"). The goal is to find a real
journal publication for entries that currently only have a preprint badge.

### B1 — List the preprint-only candidates

In `index.md`, find the `### <YEAR>` group (the one under `## Publications`, not
the separate talks/GSoC lists). Within it, an entry is a **preprint-only
candidate** when it has a preprint badge but **no** journal-DOI badge:

- *preprint badge present* = an `arXiv-...` badge (or any other preprint server,
  e.g. an HAL / SSRN / bioRxiv link).
- *journal-DOI badge absent* = no `zenodo.org/badge/doi/...` / `doi.org` badge.

An entry that already has a journal line and a DOI badge is **not** a candidate —
skip it.

Present the candidates as a **numbered list**, one line each:
`<n>. <FirstAuthor> et al., "<short title>" (arXiv:<ID>)`. Then ask the user to
pick: **"all"** or specific numbers (accept ranges/lists like `1,3,5` or `2-4`).
Do nothing else until they choose.

### B2 — Process the selected entries one by one

For each selected entry, the arXiv ID (or other preprint ID) is already in the
entry — you do **not** need the user to supply anything. Run the existing
**Steps 1–3** to discover and format a candidate published version, with this
discovery order (reverse of normal Step 1, since you start from the preprint):

1. **arXiv API** (`http://export.arxiv.org/api/query?id_list=<ID>`): check the
   `<arxiv:doi>` and `<arxiv:journal_ref>` fields. If the authors linked a
   journal DOI here, this is **authoritative** — accept it as the source.
2. **OpenAlex**: try `https://api.openalex.org/works/arxiv:<ID>`; if that 404s
   (it frequently does), fall back to a title search
   `https://api.openalex.org/works?filter=title.search:<title>` and confirm the
   hit is the same paper. Look for a published `doi` whose host venue is a real
   journal (not arXiv itself).
3. **Crossref bibliographic search**
   (`https://api.crossref.org/works?query.bibliographic=<title>&rows=5`): only as
   a last resort, and only accept a hit when the **title matches closely AND the
   author last names overlap** the preprint. Otherwise treat as not found —
   never attach a DOI you are not confident belongs to this exact paper.

Once you have a candidate DOI, fetch its Crossref record
(`https://api.crossref.org/works/<DOI>`) to get journal name, volume,
pages/article-number, and the published year, then build the updated entry per
Step 3 (canonical badge order: arXiv, journal DOI, then any existing
"reproduce me!").

Then, per entry:

- **Nothing found** (all three sources came up empty or unverified): say so
  plainly — `<n>. <FirstAuthor> et al. — no published version found` — and move
  on. Do not edit anything.
- **Found**: state **where** it came from (arXiv / OpenAlex / Crossref), show the
  proposed updated entry (before/after diff of the affected lines), and **ask the
  user whether to accept it**. Apply the change only on a yes, using the Step 5
  **Update** path (add the journal line + DOI badge, reorder badges, and move the
  entry to the correct year group if the published year differs from `<YEAR>`).

While building the updated entry, also tidy the existing one:

- **Title may differ**: papers are often renamed between preprint and journal, so
  the website entry's title may not match the published one. Prefer the
  **published** title from Crossref, but show the change and let the user veto it.
- **arXiv badge hygiene**: fix a badge whose visible label (`arXiv-<ID>`) or alt
  text disagrees with the linked ID, and normalize the link to the canonical
  `https://arxiv.org/abs/<ID>` form (drop `/pdf/` and any `vN` version suffix).
  The user may also ask for this fix on an entry that stays a preprint.

Keep the per-entry exchanges compact; the user is reviewing several in a row.

### B3 — Commit

After all selected entries are processed, commit the accepted updates in a single
branch (the user is on `main`), e.g. branch `update-publications-<year>` with a
message like `Update <year> preprints with published journal info`. If only one
entry changed, prefer the single-entry style `<Authors> (<year>) published in
<Journal>`. End with the required co-author trailer. **Do not push.** If nothing
was accepted, make no commit and just report the summary.
