# Repolex Knowledge Graph of python-trio/python-trio.github.io

RDF knowledge graph data for [python-trio/python-trio.github.io](https://github.com/python-trio/python-trio.github.io), parsed by [repolex](https://repolex.ai).

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
rlex download python-trio/python-trio.github.io
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 25fecb307ae600b8be7a1a19623099d2abe59c4e
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 25fecb307ae600b8be7a1a19623099d2abe59c4e
│           └── chunk-001.nq.gz
├── blob
│   ├── 00e77bd79be44872c0b29256b03799c2fb00c10d.nq.gz
│   ├── 0e5c5f8047718f2c021fbf24be10ea4566fde0aa.nq.gz
│   ├── 231d5d0d5aa260299c1a7a64c7cb992e52279673.nq.gz
│   ├── 26bcb4c9dcd209119f4c82e61fb8381cbf325332.nq.gz
│   ├── 473c65220c241bf621a1e00a468413dbe4b77b68.nq.gz
│   ├── 6441e08cb34e5593952ae5b8f5f5552598f4d9c5.nq.gz
│   ├── 8dd7539e4b6bfedb81e0f142963f28aaec5716cb.nq.gz
│   ├── 998a3357e8c9f6b7b50f3a7ab5670a53b8ced5da.nq.gz
│   └── fa5a12ed2a6a690b1c4e15837b5c788a0513b314.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 25fecb307ae600b8be7a1a19623099d2abe59c4e.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 15 files
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

[python-trio/python-trio.github.io](https://github.com/python-trio/python-trio.github.io)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
