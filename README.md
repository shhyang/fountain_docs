<<<<<<< Updated upstream
# Fountain docs

Brief introduction site for the [Fountain library project](https://github.com/shhyang/fountain_engine).
=======
# Fountain Library Project (docs site)
>>>>>>> Stashed changes

Static site for the [Fountain library project](https://github.com/shhyang/fountain_docs): Rust crates for fountain codes and erasure-coding schemes—a reusable engine, schemes (LT and Raptor-style), and utilities for testing and benchmarking.

<<<<<<< Updated upstream
Place the fountain engine v1 documentation PDF here:

- **Path:** `docs/engine_v1.pdf`
- The front page links to it as "Fountain engine v1 documentation (PDF)".
=======
Live site (GitHub Pages): `https://shhyang.github.io/fountain_docs/` (or `https://<username>.github.io/fountain_docs/` after you enable Pages).

## Published crates (same as the front page)
>>>>>>> Stashed changes

| Crate | Role | Crates.io | GitHub |
|-------|------|-----------|--------|
| **fountain_engine** | Core fountain code engine | [link](https://crates.io/crates/fountain_engine) | [shhyang/fountain_engine](https://github.com/shhyang/fountain_engine) |
| **fountain_utility** | Data operators and testing utilities | [link](https://crates.io/crates/fountain_utility) | [shhyang/fountain_utility](https://github.com/shhyang/fountain_utility) |
| **fountain_scheme** | Configurable schemes (LT, LDPC-LT, HDPC-LT, systematic) on `fountain_engine` | [link](https://crates.io/crates/fountain_scheme) | [shhyang/fountain_scheme](https://github.com/shhyang/fountain_scheme) |

Additional crates (`raptor_10`, `raptor_q`) may be published as the ecosystem evolves.

## Project documentation (PDFs)

Paths match [`index.html`](index.html):

- **`docs/doc-engine.pdf`** — Fountain engine and utility usage  
- **`docs/doc-scheme.pdf`** — Fountain code scheme introduction  

## Getting started

Try the examples and tests in the [`fountain_scheme`](https://github.com/shhyang/fountain_scheme) repository.

## Updating the PDFs (from the monorepo)

The PDFs are generated from Org sources in the main library repository. From that repo’s root, run `scripts/sync_fountain_docs_pdfs.sh` (see that script for prerequisites). It exports the Org files to PDF, copies them into `docs/` here, and creates a commit in this repository.

## GitHub Pages

1. In this repo: **Settings → Pages**.
2. **Source:** Deploy from a branch.
3. **Branch:** `main` (or `master`) → `/ (root)`.
4. Save.

No build step: static HTML (`index.html`), CSS (`style.css`), and PDFs under `docs/`.
