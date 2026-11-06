# Repolex Knowledge Graph of sphinx-contrib/phpdomain

RDF knowledge graph data for [sphinx-contrib/phpdomain](https://github.com/sphinx-contrib/phpdomain), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/phpdomain
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 8a9860b49b6c440abcc022ce48b07b01e58c4f4a
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 8a9860b49b6c440abcc022ce48b07b01e58c4f4a
│           └── chunk-001.nq.gz
├── blob
│   ├── 125767c15f1d18b7791f727ad4f66a2e28cbd4df.nq.gz
│   ├── 2005720ee036f2f84e64b3981efce604e4d3228b.nq.gz
│   ├── 2112e476a9232d684e3533ecf83ebf4b5084942c.nq.gz
│   ├── 37273260b34ff9ce03b3b4ec4641cf4fae9183f1.nq.gz
│   ├── 37467bdc4752a31da7763d7cf24051ab5a8a4307.nq.gz
│   ├── 4310ae15746fc35a2a0fe40d0d7cf7919c5ac17b.nq.gz
│   ├── 5c643ef1eb3db28491e68ca015a7135eb1f57be0.nq.gz
│   ├── 66a9920c0cb4a4624c987883c0e3ad570c89739a.nq.gz
│   ├── 6ad727d49f3bdd4aaaacfd912a1e9da2238eca81.nq.gz
│   ├── 923bc3d0847b12abbeabfec3f696ead7d6a62242.nq.gz
│   ├── 9456db6a3252e4ba05cd844f9994d9662ab481ac.nq.gz
│   ├── a560d7597d33842d3c3e7a19557d43c26576c13a.nq.gz
│   ├── a654c2697f8b53402226c59b684f60f82b7510c4.nq.gz
│   ├── b5a7dc29ef0f7f3593b1c61cfc5dfe8a17d3918c.nq.gz
│   ├── deb030fe93095b53394f9ced9608f5145ec18151.nq.gz
│   ├── f0908b85ac10a6e30f6aac8afed31eb0fb1d3214.nq.gz
│   └── f61d988721c77634c75cb33586a7521fbb81817c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 8a9860b49b6c440abcc022ce48b07b01e58c4f4a.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 23 files
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

[sphinx-contrib/phpdomain](https://github.com/sphinx-contrib/phpdomain)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
