# Repolex Knowledge Graph of gruns/icecream

RDF knowledge graph data for [gruns/icecream](https://github.com/gruns/icecream), parsed by [repolex](https://repolex.ai).

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
rlex download gruns/icecream
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 2e09b0dc674bc4375f34b5254d15569569603ee1
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 2e09b0dc674bc4375f34b5254d15569569603ee1
│           └── chunk-001.nq.gz
├── blob
│   ├── 0f34d6603117789060e70d7000d33452d923753e.nq.gz
│   ├── 209c3df064ce56693dce2f861ff05d20a562ad10.nq.gz
│   ├── 342c56db0ab98d26d1a2ac8326e417d9aa544d6d.nq.gz
│   ├── 44ffe2f730f11d73f3f7443b4b308c2295949fc6.nq.gz
│   ├── 45a39caf1e9667e6e097b14c301384bd3f92e159.nq.gz
│   ├── 487f40a13f0da6a83953b6585c1fb6df937cedd6.nq.gz
│   ├── 5ace4600a1f26e6892982f3e2f069ebfab108d87.nq.gz
│   ├── 811f09adc03d1861b479f62d9072f7cd9b39411a.nq.gz
│   ├── 8ce12eb0da77446a413d95fe258eb2b23385dbac.nq.gz
│   ├── 96b6dc07dc1aac01cb9f2e59764be2b8ab4d1359.nq.gz
│   ├── 9809d45604ca225d691b2592a42e9db80d18353e.nq.gz
│   ├── 9fdbe014df3fd0e04959fc74c551b719a71f469e.nq.gz
│   ├── a9eb729aafbeb552fcf6eaf89a07a0aa84520934.nq.gz
│   ├── b577be354ab1304d6661ce2e253abacadff0e094.nq.gz
│   ├── b6a314a36705886457054d0f4cca9e7e1f75bf15.nq.gz
│   ├── b7fe4a3e7758aae188caa6210492b4528d35287d.nq.gz
│   ├── c0482f737c63aac2af8da9d914d7d99d5d3795e6.nq.gz
│   ├── c217f33a50ba0d159c6cc14187d894215b08a75f.nq.gz
│   ├── c304037c4d7cb31f51ffb489d7b9a3a90cc7d292.nq.gz
│   ├── cf03ac0fcdeae4bc9c3e5037c03563d083a1517a.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── ef9e2d189a6fd6a4075368bb9209b8e8438f01b8.nq.gz
│   ├── f71ccb6388782c57766ad2cc8eafbcb1d921b466.nq.gz
│   └── f93b0decfd230b65fe58c371ee6045913245c936.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 2e09b0dc674bc4375f34b5254d15569569603ee1.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 32 files
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

[gruns/icecream](https://github.com/gruns/icecream)

---
*Parsed on 2026-10-18 by [repolex](https://repolex.ai)*
