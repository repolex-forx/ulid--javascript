# Repolex Knowledge Graph of ulid/javascript

RDF knowledge graph data for [ulid/javascript](https://github.com/ulid/javascript), parsed by [repolex](https://repolex.ai).

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
rlex download ulid/javascript
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 11c2067821ee19e4dc787ca4e0125a025485edc6
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 11c2067821ee19e4dc787ca4e0125a025485edc6
│           └── chunk-001.nq.gz
├── blob
│   ├── 03d2ceb640597dd49491e93c39831a8e72efe8a1.nq.gz
│   ├── 0e7e64be212e93a45ac761339372af23dca25b41.nq.gz
│   ├── 0ebff9b33715e6df22bbf8804f00d7c15b4ae3b5.nq.gz
│   ├── 1cb63a2718e82a2f31f5bb18f44439aad5f5a7cb.nq.gz
│   ├── 2715941563cde4f799d15babd620568ab979cbe6.nq.gz
│   ├── 3bd2c5bc1d8fcb4862196d9d1294762f313413d6.nq.gz
│   ├── 5f0c51f6c4551115bf399509f73e24d2ad46bfbe.nq.gz
│   ├── 68c92eaa8ea4e14c13547a2c4b9b5ade0570fb84.nq.gz
│   ├── 889650649d176feaa1d2f4cb3412dfb1c4ab07fc.nq.gz
│   ├── 8c3ed34cbf280b654e5bff091d08c41fdbc9bbf3.nq.gz
│   ├── 8e4868cca7175c4324fefd20ad6838daccf534e8.nq.gz
│   ├── 9fe9f535bc152c545a616fdae03f646f79b11f8f.nq.gz
│   ├── a2707247550d87c3491d99984dd381752fe1b7d0.nq.gz
│   ├── a7b32f36c8fddb0c6ee449987f0984751faf6210.nq.gz
│   ├── c308ed0c0e7c7f11bd558a807b8331c607523e9e.nq.gz
│   ├── c711d324c079ba8c1c8ad977744af0a48e02bb03.nq.gz
│   ├── c9b96016802fb693dedc2e513764a6f01f19eb48.nq.gz
│   ├── cf7da0813e0f46c2d9d3eae935b2bc5c884da088.nq.gz
│   ├── da2160d2f8e224fcfbf871cca3952e0a5d4da302.nq.gz
│   ├── db74bb8cfe349b5bf8ea057e277bb50695036eb4.nq.gz
│   ├── f237ddf58ed4ffa78778ce7f9339b647c177a932.nq.gz
│   ├── f99852e89c1455a030fda7ed8ae42091bff27e04.nq.gz
│   └── ff002132d11c79ce163f07aa279015f0382b68d0.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 11c2067821ee19e4dc787ca4e0125a025485edc6.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 31 files
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

[ulid/javascript](https://github.com/ulid/javascript)

---
*Parsed on 2026-11-09 by [repolex](https://repolex.ai)*
