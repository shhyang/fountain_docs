# Fountain docs
 
Brief introduction site for the [Fountain library project], published on (https://github.com/shhyang/fountain_docs).

## Add the engine PDF

Place the documentation PDF here:

- **Path:** `docs/doc-engine.pdf`
- The front page links to it as "Fountain engine v1 documentation (PDF)".

After adding the file, commit and push; the link on the site will work.

## Engine and scheme handbooks (from the monorepo)

The PDFs `docs/doc-engine.pdf` and `docs/doc-scheme.pdf` are generated from Org sources in the main library repository. From that repo’s root, run `scripts/sync_fountain_docs_pdfs.sh` (see that script for prerequisites). It exports the Org files to PDF, copies them here, and commits this repository.

## GitHub Pages

1. In this repo: **Settings → Pages**.
2. **Source:** Deploy from a branch.
3. **Branch:** `main` (or `master`) → `/ (root)`.
4. Save. The site will be at `https://<username>.github.io/fountain_docs/`.

No build step: the site is static HTML and CSS only.
