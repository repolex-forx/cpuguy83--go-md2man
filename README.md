# Repolex Knowledge Graph of cpuguy83/go-md2man

RDF knowledge graph data for [cpuguy83/go-md2man](https://github.com/cpuguy83/go-md2man), parsed by [repolex](https://repolex.ai).

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
rlex download cpuguy83/go-md2man
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 061b6c7cbecd6752049221aa15b7a05160796698
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 061b6c7cbecd6752049221aa15b7a05160796698
│           └── chunk-001.nq.gz
├── blob
│   ├── 0da6a0797acf863fdd5a1f2d4e9cbe2c9fe12526.nq.gz
│   ├── 0ec4b12c75d07021b534456c86566c9293af6576.nq.gz
│   ├── 12e550d6ce514304d6990b307363106234a73328.nq.gz
│   ├── 1cade6cef6a1cb8efdf8549d709a99734c454630.nq.gz
│   ├── 30f97c3d73abbba4440fa7c6dfc60aaa9b0c56b4.nq.gz
│   ├── 4f1070fc5b79d43ae20bec4ab94cba5583d7fa1c.nq.gz
│   ├── 502a072c0ab7c14b338aad69a07f349b358f0fc9.nq.gz
│   ├── 55d89f506884dc0dde9fd0e0053e11bd50f8d8a1.nq.gz
│   ├── 5673f5c0bc6c5d9553f4ddb8888579c27f321ae4.nq.gz
│   ├── 5f4a423d6f25ab75ed89c3e767fd0bfde46feb4a.nq.gz
│   ├── 6248294b6a15fbe8c4879bf7d7f80002acf302cb.nq.gz
│   ├── 77b7be590e900e5d269837d9143b7451e3372cd4.nq.gz
│   ├── b9fc4dfdb52a559d4d6a3f8757c74c40721a3f09.nq.gz
│   ├── c1e7d7e61b8b28776ae2cb620374d4fea3f2c267.nq.gz
│   ├── c7ff868ad8288c394e04e6e6b918df722f9f71c0.nq.gz
│   └── ccc2c64ffa3ca61f323c12c7d9d72add492928ce.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 061b6c7cbecd6752049221aa15b7a05160796698.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 24 files
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

[cpuguy83/go-md2man](https://github.com/cpuguy83/go-md2man)

---
*Parsed on 2026-11-09 by [repolex](https://repolex.ai)*
