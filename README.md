# Repolex Knowledge Graph of pandas-dev/pandas-benchmarks

RDF knowledge graph data for [pandas-dev/pandas-benchmarks](https://github.com/pandas-dev/pandas-benchmarks), parsed by [repolex](https://repolex.ai).

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
rlex download pandas-dev/pandas-benchmarks
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 6cceefa00d05e03f7ffbf06e54185ba0b9f211b0
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 6cceefa00d05e03f7ffbf06e54185ba0b9f211b0
│           └── chunk-001.nq.gz
├── blob
│   ├── 95aebb37c1f15fe52b7be103cf03553c60fd346a.nq.gz
│   └── df4945d3b8c08cdaa7a45de1ff7cb303eb72dd2d.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 6cceefa00d05e03f7ffbf06e54185ba0b9f211b0.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 9 files
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

[pandas-dev/pandas-benchmarks](https://github.com/pandas-dev/pandas-benchmarks)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
