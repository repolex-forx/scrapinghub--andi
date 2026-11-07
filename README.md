# Repolex Knowledge Graph of scrapinghub/andi

RDF knowledge graph data for [scrapinghub/andi](https://github.com/scrapinghub/andi), parsed by [repolex](https://repolex.ai).

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
rlex download scrapinghub/andi
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 5b7f1094a5526a016477a3d1c3f7617909f3bbbf
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 5b7f1094a5526a016477a3d1c3f7617909f3bbbf
│           └── chunk-001.nq.gz
├── blob
│   ├── 0800eec22fe01d20319d091764832857622f636d.nq.gz
│   ├── 0d79dded8d6a5710fb67812fce4da8e8ad73c572.nq.gz
│   ├── 176b175cbd821758dfeeef6267f9910a11332267.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 2c55784e7789aaa55ea30b46627f7707bf06c7cb.nq.gz
│   ├── 2da5e1b8a641eaded9f0ee2a782d2453def71615.nq.gz
│   ├── 45e8fac7c42e7ffa359f96c202d4414dd0cc1f19.nq.gz
│   ├── 623d48cfa6b6f2ba551dde2435254ed5a1b63862.nq.gz
│   ├── 6dcd66838990ce27792713d5d46c2477c36b888f.nq.gz
│   ├── 76ad5eeb8f54b20bc63dce5a025f3cea23b6b624.nq.gz
│   ├── 77d79d673e56a30125741352c72630368a33a7f5.nq.gz
│   ├── 79806187dad8abc4be037304b4bf0bdb631e2f15.nq.gz
│   ├── 7b5af3b43843c9af65c09733f80719465264507a.nq.gz
│   ├── 80e845d660a96cebb8c014ca123753081db40d82.nq.gz
│   ├── 8c0386d12a3744dcc93dd642ef49de515f371f8b.nq.gz
│   ├── 98b0c09b773cf8ae18d32b77be69a26c7faaf7ba.nq.gz
│   ├── 9919c481f450ca5cb340e426287cebb9fcdc77ee.nq.gz
│   ├── 99e19f89938cc603669c415a52b5176c0c99cb1c.nq.gz
│   ├── 9b48c899204b31005fb9b7bf6406230d7dc598ad.nq.gz
│   ├── 9f98a0ebf1c4394f8cd3c7c9b46d5130e26cfa7b.nq.gz
│   ├── a904a7d5d747c5e2119f463a0656190200d0fea6.nq.gz
│   ├── b7a6c6bb610ef340f49da793810d7d86343475cb.nq.gz
│   ├── d1e66199152fce09454660a8a0244d4926094d43.nq.gz
│   ├── d8aa6b984fa2c4c4891f114100d205ad99801b34.nq.gz
│   ├── e51f046cffa876a6c6f057d2774287de443b905b.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 5b7f1094a5526a016477a3d1c3f7617909f3bbbf.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 34 files
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

[scrapinghub/andi](https://github.com/scrapinghub/andi)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
