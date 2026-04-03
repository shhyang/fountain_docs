# Fountain Library Project (docs site)
 
Brief introduction site for the [Fountain library project], published on (https://github.com/shhyang/fountain_docs).

Static site for the [Fountain library project]: Rust crates for fountain codes and erasure-coding schemes—a reusable engine, schemes (LT and Raptor-style), and utilities for testing and benchmarking.

Live site (GitHub Pages): `https://shhyang.github.io/fountain_docs/` (or `https://<username>.github.io/fountain_docs/` after you enable Pages).

## Published crates (same as the front page)

| Crate | Role | Crates.io | GitHub |
|-------|------|-----------|--------|
| **fountain_engine** | Core fountain code engine | [link](https://crates.io/crates/fountain_engine) | [shhyang/fountain_engine](https://github.com/shhyang/fountain_engine) |
| **fountain_utility** | Data operators and testing utilities | [link](https://crates.io/crates/fountain_utility) | [shhyang/fountain_utility](https://github.com/shhyang/fountain_utility) |
| **fountain_scheme** | Configurable schemes (LT, LDPC-LT, HDPC-LT, systematic) on `fountain_engine` | [link](https://crates.io/crates/fountain_scheme) | [shhyang/fountain_scheme](https://github.com/shhyang/fountain_scheme) |

## Project documentation (PDFs)

Paths match [`index.html`](index.html):

- **`docs/doc-engine.pdf`** — Fountain engine and utility usage  
- **`docs/doc-scheme.pdf`** — Fountain code scheme introduction  

## Updating the PDFs (from the monorepo)

The PDFs are generated from Org sources in the main library repository. From that repo’s root, run `scripts/sync_fountain_docs_pdfs.sh` (see that script for prerequisites). It exports the Org files to PDF, copies them into `docs/` here, and creates a commit in this repository.

## GitHub Pages

1. In this repo: **Settings → Pages**.
2. **Source:** Deploy from a branch.
3. **Branch:** `main` (or `master`) → `/ (root)`.
4. Save.

No build step: static HTML (`index.html`), CSS (`style.css`), and PDFs under `docs/`.
