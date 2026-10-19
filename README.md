# Repolex Knowledge Graph of mitsuhiko/phpserialize

RDF knowledge graph data for [mitsuhiko/phpserialize](https://github.com/mitsuhiko/phpserialize), parsed by [repolex](https://repolex.ai).

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
rlex download mitsuhiko/phpserialize
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 46a7e5d443757dedaaff4f6b1b8ae5e020210e0e
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 46a7e5d443757dedaaff4f6b1b8ae5e020210e0e
│           └── chunk-001.nq.gz
├── blob
│   ├── 036cfb4c36438e1b9671d51ed8fc6cc3b9197abd.nq.gz
│   ├── 49f17aff5b991adc0d2b30f01948e9ba1f01a5f0.nq.gz
│   ├── 4b7abf0c9b9855a3b4ab79862043eefafd561a12.nq.gz
│   ├── 855285711523ad7fe2f0bfeb92d6f803a88951a8.nq.gz
│   ├── 861a9f554263efb088d8636c4f17a30696e495ad.nq.gz
│   ├── 9a72537dd03963edac5876568bd3ffb4b0ad8940.nq.gz
│   ├── ea49e64a2cf17a3aacdaf67c214b09865e54ac99.nq.gz
│   └── f6d7066986e66418fe4f2132ce292754d675dc6a.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 46a7e5d443757dedaaff4f6b1b8ae5e020210e0e.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 16 files
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

[mitsuhiko/phpserialize](https://github.com/mitsuhiko/phpserialize)

---
*Parsed on 2026-10-19 by [repolex](https://repolex.ai)*
