# Repolex Knowledge Graph of Python-Markdown/github-links

RDF knowledge graph data for [Python-Markdown/github-links](https://github.com/Python-Markdown/github-links), parsed by [repolex](https://repolex.ai).

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
rlex download Python-Markdown/github-links
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── b2bd50516493f0ea4ab1426c1db5d4702488b8bd
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── b2bd50516493f0ea4ab1426c1db5d4702488b8bd
│           └── chunk-001.nq.gz
├── blob
│   ├── 027433a43b9eff987191b7cc632979230a8daa5d.nq.gz
│   ├── 0f507105abf3b51bb2056f84ddc030cb6246d0b6.nq.gz
│   ├── 342590c7d954a62062ef7c9801520ee25999422e.nq.gz
│   ├── 4a118fa32cc42253ebac9c4549477aa5cf15c8be.nq.gz
│   ├── 72364f99fe4bf8d5262df3b19b33102aeaa791e5.nq.gz
│   ├── 76d47d2ee9eeeb6d91d428c4c2c67a5d7f1de744.nq.gz
│   ├── a4924367200350d28ffb4ffb87ec19d6b6d97e69.nq.gz
│   ├── c1020edec93176d7c9780dce9265b1a021b8d24a.nq.gz
│   └── f4c7b4a8e2e83326163f50efb5d197474c95f305.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── b2bd50516493f0ea4ab1426c1db5d4702488b8bd.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 17 files
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

[Python-Markdown/github-links](https://github.com/Python-Markdown/github-links)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
