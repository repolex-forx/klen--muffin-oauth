# Repolex Knowledge Graph of klen/muffin-oauth

RDF knowledge graph data for [klen/muffin-oauth](https://github.com/klen/muffin-oauth), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [rlex](https://github.com/repolex-ai/rlex) query tool:

```bash
cargo install --git https://github.com/repolex-ai/rlex
```

Verify the install:

```bash
rlex --help
```

**rlex is designed to be used primarily by LLMs in a terminal.** Start up your favorite AI assistant and ask it to use rlex. It handles the SPARQL — you just ask questions in plain English.

To load this repo's data:

```bash
rlex download klen/muffin-oauth
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 3b400215321f20fbbd6baf65261dae41687b5f01
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 3b400215321f20fbbd6baf65261dae41687b5f01
│           └── chunk-001.nq.gz
├── blob
│   ├── 0a6ee958310ca78a98bf4803c291d5898c7fd5b4.nq.gz
│   ├── 0b2e907c89333ea1b1c45cf476f5afdd63c69c08.nq.gz
│   ├── 23c5c150f58bdd129447223d88288e859f8cccb1.nq.gz
│   ├── 36801b5f79acd9b92b76b0eb7e1469406bd796a0.nq.gz
│   ├── 3d3de9177b065ccd2b82e03a2cd70dd8b0e5323a.nq.gz
│   ├── 440f2e5a3dddaeb4a66081ca76bf31b5922fba82.nq.gz
│   ├── 56d44bac4f03d59bb9905afc2c1e70cae481bd31.nq.gz
│   ├── 5f1d5686f3dc12105665875988bbe0b90d32c2bc.nq.gz
│   ├── 60bb6ada845985c9383cf9b8e33cef6aa9a91972.nq.gz
│   ├── 62aaac0863a0290cd8ddf2041f6153ae4bf0dc84.nq.gz
│   ├── 635ad4bc16d9f355b9d2237233fc3660ffba8cfc.nq.gz
│   ├── 656da66e0b15403099afea7a23b4c84a1953d841.nq.gz
│   ├── 666ce2a519fd8f0c3599a11f968422b82612ca92.nq.gz
│   ├── 66f733d918398cdf3fecfaf5e452d1e1322a9a7a.nq.gz
│   ├── 78df056a6afd6b2f7c5a8695635380a19f30acd9.nq.gz
│   ├── 7a164db40479afa0234991286706d2c0dc36cbf1.nq.gz
│   ├── 7a3f07ab83552f47a8705fa5d22729a324a2f71a.nq.gz
│   ├── 85e59ba202621041a955468f70385393342d19d0.nq.gz
│   ├── 89c602737e3c362274bb78e92b8378cbfcd50087.nq.gz
│   ├── 8a35a0310e3f6eb7f27fde9ae1b865f91a95f39c.nq.gz
│   ├── 99e54b2c98c0a9e7b472bbabd6181fb4856c3227.nq.gz
│   ├── b081a7bfac92578ee2aebee6bb00051d364d1335.nq.gz
│   ├── b8bd22f329babe3cc625c36f759b8a4b761180c1.nq.gz
│   ├── ce48f87110f5a00c4f3320f9ed0c8e630cb23daf.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e728d03676c20ba87a39556e60b642f5df17ebde.nq.gz
│   └── ef23051ba28a3e87238a94de1f097f9bbd894ac8.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 3b400215321f20fbbd6baf65261dae41687b5f01.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 34 files
```

| Directory | What it contains |
|-----------|-----------------|
| `blob/` | Per-file AST graphs, content-addressed by git blob SHA. Each file in the source repo gets its own graph. |
| `aggregate/ast/` | Combined AST graph per parsed commit. Merges all blob graphs for a snapshot of the entire codebase at that point. |
| `aggregate/lsp/` | Language Server Protocol enrichment: resolved symbols, definitions, references, and type information. |
| `aggregate/dataflow/` | Interprocedural data flow edges between functions and modules. |
| `aggregate/repolex/` | Combined graph (AST + LSP + dataflow) per commit. |
| `commit/` | Git commit metadata (author, date, message, parent links). |
| `branch/` | Branch metadata. |
| `tag/` | Tag metadata. |
| `filetree/` | File tree snapshots per commit (which files existed and their blob SHAs). |
| `audit/` | Code architecture and graph audit reports per commit. |

## Source repository

[klen/muffin-oauth](https://github.com/klen/muffin-oauth)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
