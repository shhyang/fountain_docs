# Fountain Library Project (docs site)

Maintainer notes for the [Fountain library project](https://github.com/shhyang/fountain_docs) static site. The public landing page is [`index.html`](index.html) (mirrors the content visitors see on GitHub Pages).

Rust crates for fountain codes and erasure-coding schemes: a reusable engine, schemes (LT and Raptor-style), and utilities for testing and benchmarking.

**Live site:** [https://shhyang.github.io/fountain_docs/](https://shhyang.github.io/fountain_docs/)

## Published crates (same as the front page)

| Crate | Role | docs.rs | Crates.io | GitHub |
|-------|------|---------|-----------|--------|
| **fountain_engine** | Core fountain code engine | [docs.rs](https://docs.rs/fountain_engine) | [crates.io](https://crates.io/crates/fountain_engine) | [shhyang/fountain_engine](https://github.com/shhyang/fountain_engine) |
| **fountain_utility** | Data operators and testing utilities | [docs.rs](https://docs.rs/fountain_utility) | [crates.io](https://crates.io/crates/fountain_utility) | [shhyang/fountain_utility](https://github.com/shhyang/fountain_utility) |
| **fountain_scheme** | Configurable schemes (LT, LDPC-LT, HDPC-LT, systematic) on `fountain_engine` | [docs.rs](https://docs.rs/fountain_scheme) | [crates.io](https://crates.io/crates/fountain_scheme) | [shhyang/fountain_scheme](https://github.com/shhyang/fountain_scheme) |
| **fountain_raptor_q** | RFC 6330 RaptorQ scheme crate | [docs.rs](https://docs.rs/fountain_raptor_q) | [crates.io](https://crates.io/crates/fountain_raptor_q) | [wutongabc/fountain_raptor_q](https://github.com/wutongabc/fountain_raptor_q) |
| **fountain_raptor_10** | RFC 5053 Raptor-10 scheme crate | [docs.rs](https://docs.rs/fountain_raptor_10) | [crates.io](https://crates.io/crates/fountain_raptor_10) | [wutongabc/fountain_raptor_10](https://github.com/wutongabc/fountain_raptor_10) |

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
