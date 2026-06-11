# Fountain Library Project (docs site)

Maintainer notes for the [Fountain library project](https://github.com/shhyang/fountain_docs) static site. The public landing page is [`index.html`](index.html) (mirrors the content visitors see on GitHub Pages).

Rust crates for fountain codes: a reusable engine, schemes (LT and Raptor-style), utilities for testing and benchmarking, optional high-performance operators, and rateless UDP file transfer (`fountain_transfer`).

**Live site:** [https://shhyang.github.io/fountain_docs/](https://shhyang.github.io/fountain_docs/)

## Getting started (same as the front page)

1. Add `fountain_engine` plus one scheme crate (`fountain_scheme`, `fountain_raptor_q`, or `fountain_raptor_10`) to your `Cargo.toml`.
2. Optional: add experimental `fountain_operators` from GitHub (requires `fountain_engine` 1.3+).
3. Try `fountain_transfer` for rateless UDP file transfer ([quick start](https://github.com/shhyang/fountain_transfer#quick-start)).
4. Read `docs/doc-engine.pdf` and `docs/doc-scheme.pdf` (paths match [`index.html`](index.html)).

## Published crates (same as the front page)

| Crate | Role | docs.rs | Crates.io | GitHub |
|-------|------|---------|-----------|--------|
| **fountain_engine** | Core fountain code engine | [docs.rs](https://docs.rs/fountain_engine) | [crates.io](https://crates.io/crates/fountain_engine) | [shhyang/fountain_engine](https://github.com/shhyang/fountain_engine) |
| **fountain_utility** | In-memory operators, padding wrappers, testing utilities | [docs.rs](https://docs.rs/fountain_utility) | [crates.io](https://crates.io/crates/fountain_utility) | [shhyang/fountain_utility](https://github.com/shhyang/fountain_utility) |
| **fountain_scheme** | Configurable schemes (LT, LDPC-LT, HDPC-LT, systematic) on `fountain_engine` | [docs.rs](https://docs.rs/fountain_scheme) | [crates.io](https://crates.io/crates/fountain_scheme) | [shhyang/fountain_scheme](https://github.com/shhyang/fountain_scheme) |
| **fountain_raptor_q** | RFC 6330 RaptorQ scheme crate | [docs.rs](https://docs.rs/fountain_raptor_q) | [crates.io](https://crates.io/crates/fountain_raptor_q) | [wutongabc/fountain_raptor_q](https://github.com/wutongabc/fountain_raptor_q) |
| **fountain_raptor_10** | RFC 5053 Raptor-10 scheme crate | [docs.rs](https://docs.rs/fountain_raptor_10) | [crates.io](https://crates.io/crates/fountain_raptor_10) | [wutongabc/fountain_raptor_10](https://github.com/wutongabc/fountain_raptor_10) |

## GitHub-only crates

| Crate | Role | Distribution | GitHub |
|-------|------|--------------|--------|
| **fountain_operators** | **Experimental.** High-performance `DataOperator` backends (`SlabDataOperator`, `SimdDataOperator`, GF(256) kernels, replay/testing). API may change. Requires `fountain_engine` **1.3+**. | Git dependency (not on Crates.io) | [shhyang/fountain_operators](https://github.com/shhyang/fountain_operators) |
| **fountain_transfer** | Rateless UDP file transfer: `fountain_transfer_core` library (dual-codec facade, RFC packet codec) + `fountain` CLI (`send` / `recv`). MIT; links AGPL `fountain_engine` in-process. | GitHub workspace (not on Crates.io yet) | [shhyang/fountain_transfer](https://github.com/shhyang/fountain_transfer) |

Example dependency (from the [operators README](https://github.com/shhyang/fountain_operators#usage)):

```toml
fountain_engine = "1.3"
fountain_operators = { git = "https://github.com/shhyang/fountain_operators", features = ["simd"] }
```

Raptor performance examples (`raptor_q_performance`, `raptor_10_performance`) use `fountain_operators` as an optional **dev-dependency** with the same Git URL. See the [operators README](https://github.com/shhyang/fountain_operators#end-to-end-examples-raptor-crates) for run commands.

Clone [fountain_transfer](https://github.com/shhyang/fountain_transfer) for loopback UDP transfer (`fountain send` / `fountain recv`); see its [README quick start](https://github.com/shhyang/fountain_transfer#quick-start).

## Project documentation (PDFs)

Paths match [`index.html`](index.html):

- **`docs/doc-engine.pdf`** — Fountain engine and utility usage
- **`docs/doc-scheme.pdf`** — Fountain code scheme introduction

Operator guide source in the monorepo: `docs/doc-operators.org` (PDF not yet synced to this site).

## Updating the PDFs (from the monorepo)

The PDFs are generated from Org sources in the main library repository. From that repo’s root, run `scripts/sync_fountain_docs_pdfs.sh` (see that script for prerequisites). It exports the Org files to PDF, copies them into `docs/` here, and creates a commit in this repository.

When adding a new crate to the landing page, edit **`index.html`** and this **`README.md`**, then commit in `publish/fountain_docs` (no PDF rebuild required).

## GitHub Pages

1. In this repo: **Settings → Pages**.
2. **Source:** Deploy from a branch.
3. **Branch:** `main` (or `master`) → `/ (root)`.
4. Save.

No build step: static HTML (`index.html`), CSS (`style.css`), and PDFs under `docs/`.
