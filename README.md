# Repolex Knowledge Graph of block/renovate-config

RDF knowledge graph data for [block/renovate-config](https://github.com/block/renovate-config), parsed by [repolex](https://repolex.ai).

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
rlex download block/renovate-config
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 2e51a088c18cd126525b9c3440d6007d5d1e6d38
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 2e51a088c18cd126525b9c3440d6007d5d1e6d38.nq.gz
│   └── repolex
│       └── 2e51a088c18cd126525b9c3440d6007d5d1e6d38
│           └── chunk-001.nq.gz
├── blob
│   ├── 97fa4add338fa1e2e4d6b08d2bce6561a457d653.nq.gz
│   └── 9ab05b22f407ca72dec4365c2624c3b09cec97e2.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 2e51a088c18cd126525b9c3440d6007d5d1e6d38.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 10 files
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

[block/renovate-config](https://github.com/block/renovate-config)

---
*Parsed on 2026-10-08 by [repolex](https://repolex.ai)*
