# Repolex Knowledge Graph of simonw/datasette-cluster-map

RDF knowledge graph data for [simonw/datasette-cluster-map](https://github.com/simonw/datasette-cluster-map), parsed by [repolex](https://repolex.ai).

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
rlex download simonw/datasette-cluster-map
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── d6b2362cbd97bc6a26f2ffeb8da7cbf05f6751a7
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── d6b2362cbd97bc6a26f2ffeb8da7cbf05f6751a7
│           └── chunk-001.nq.gz
├── blob
│   ├── 074199dc559c18ea0ba659f947ea98917de2dd85.nq.gz
│   ├── 222861c341540db6785e10c2b6461d5cbc94a6eb.nq.gz
│   ├── 3524bec4a5b1e3dec59561d217f41f29ee777056.nq.gz
│   ├── 697bd4c24897e116fdf3e4381216b717ac767178.nq.gz
│   ├── 7d146d2fae2274420d93b37621b49bf9ceedbb90.nq.gz
│   ├── 8dada3edaf50dbc082c9a125058f25def75e625a.nq.gz
│   ├── 9c942c71db9f08a82be61e58baa0e4942e2d4c9a.nq.gz
│   ├── b6c448c630f435014be68e2caafe5dd79b2a2aab.nq.gz
│   ├── c7d0d27e158b9229f2ad83f65fdffdb20f45da89.nq.gz
│   ├── ce3062b8185c3e0e5bd4ecc3b5b2f1148369e94c.nq.gz
│   ├── cf063cdafe0b48571a71dd46ac7c20b988e9e84c.nq.gz
│   ├── d18f4ea1e7545dca9c84e094c22ed7587f52e213.nq.gz
│   ├── db0bf3a7a513dddce879c537c058e48fcd1bf86f.nq.gz
│   └── e8e1705cc661ff587ca6c8336ea4dd05485d75e9.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── d6b2362cbd97bc6a26f2ffeb8da7cbf05f6751a7.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 22 files
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

[simonw/datasette-cluster-map](https://github.com/simonw/datasette-cluster-map)

---
*Parsed on 2026-10-12 by [repolex](https://repolex.ai)*
