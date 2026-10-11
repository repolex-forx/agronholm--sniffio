# Repolex Knowledge Graph of agronholm/sniffio

RDF knowledge graph data for [agronholm/sniffio](https://github.com/agronholm/sniffio), parsed by [repolex](https://repolex.ai).

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
rlex download agronholm/sniffio
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 95190ad58001f2ce3327ecd600380887b63dd8a7
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 95190ad58001f2ce3327ecd600380887b63dd8a7
│           └── chunk-001.nq.gz
├── blob
│   ├── 02945a947527a9bfb396d0cd35ffee22eda665bb.nq.gz
│   ├── 104c402ebf17ef55f9cdca2114f0a4449f6dd039.nq.gz
│   ├── 133b89f554a3ae181dc07bf5dbd9b69cc316b48a.nq.gz
│   ├── 21df1c65ad42a0bee76406a7258a89e36b8eeb2b.nq.gz
│   ├── 291bfeaa3b207e4173c50080f22cfb473363ee5a.nq.gz
│   ├── 2a62cea5a0a34136b4ab8c84089f616ac0654883.nq.gz
│   ├── 2c71c9d662a8386fb39cb4c7d1bd35c67ea1275e.nq.gz
│   ├── 47ad4b1d6f68df976d9c63307c411ebab7daa205.nq.gz
│   ├── 4cd8acfcac6fac8c3f21168ab5280a585394697d.nq.gz
│   ├── 4edd4b18b3f9a2893c3d0a37e5e747a5f09cebe7.nq.gz
│   ├── 51f3442917839f8e0f0cccb52b3c10968ad0779e.nq.gz
│   ├── 63f2f19e409c7f4b3c6c064022e8f104227873aa.nq.gz
│   ├── 6742196cb2535493adbb7941ab0a279c0f39b0e2.nq.gz
│   ├── 67898ba6f5cffa770a3110d8c996c8203cbbdc26.nq.gz
│   ├── 6d45a38edcd4b10c2e73f352e4cf90167f4423a0.nq.gz
│   ├── 76a28299ab326f25fe6d4285c018d51a3127236d.nq.gz
│   ├── 7fb30ff405a3e087b0ccaa1f554d048933b72591.nq.gz
│   ├── 93227db00343f029d1b56e3b5056502b34fdc498.nq.gz
│   ├── 938a98f24314376f217d36f45f4c8e9c17a63235.nq.gz
│   ├── 967836e11eefc747941a6ab75ffb0ba5a83e6a4a.nq.gz
│   ├── a054095a2efe5ee0cdf93ace980a09512ef88875.nq.gz
│   ├── a0f0c6f30968a2a45d19f215aef41c16716cae54.nq.gz
│   ├── aceed1fe3a3dec75afaea88eac075c253647f3e9.nq.gz
│   ├── b8bb97185926d7daed314609753173945ed4ff1a.nq.gz
│   ├── c1a7bbf218ba985b87cd1d9b23da69222894c1dd.nq.gz
│   ├── d645695673349e3947e8e5ae42332d0ac3164cd7.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── eba1b15936f1e66cdf51c745cb31f112236f672c.nq.gz
│   └── f38c5167733eb2fd1cb677450f876788a4aa603e.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 95190ad58001f2ce3327ecd600380887b63dd8a7.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 35 files
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

[agronholm/sniffio](https://github.com/agronholm/sniffio)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
