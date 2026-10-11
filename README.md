# Repolex Knowledge Graph of samuelcolvin/aicli

RDF knowledge graph data for [samuelcolvin/aicli](https://github.com/samuelcolvin/aicli), parsed by [repolex](https://repolex.ai).

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
rlex download samuelcolvin/aicli
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 56aff269b70d52a4712d9e9f6b092466066f0fba
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 56aff269b70d52a4712d9e9f6b092466066f0fba
│           └── chunk-001.nq.gz
├── blob
│   ├── 2bbe6b2b09777d5c2787bc01e79d5ecedd41b2a4.nq.gz
│   ├── 455963f41782c79a8b56535770d474fc3decb00c.nq.gz
│   ├── 483c0dd42b9cbebbeb465a4b08a69a6ffea7e67a.nq.gz
│   ├── 56ad1687bd5e804ac99b11c29e5ec08fd133e07d.nq.gz
│   ├── 5c5e77c71640eeab27f31402393840dfb0e052a1.nq.gz
│   ├── 61ef40189c765733a20a0c3f7168fa22e29fbb69.nq.gz
│   ├── 8628b976776b4171bdf1c6e2fb41b592d76c4e89.nq.gz
│   ├── 92457058b515165318d0810a8e51b92952bb598a.nq.gz
│   ├── a7c11769abd737e2ab564dacccf5e1e6dfcc989d.nq.gz
│   └── f2eaa8f399a589ebca97095f227e0f6f630c9e83.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 56aff269b70d52a4712d9e9f6b092466066f0fba.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 17 files
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

[samuelcolvin/aicli](https://github.com/samuelcolvin/aicli)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
