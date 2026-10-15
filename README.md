# Repolex Knowledge Graph of jupyterhub/systemdspawner

RDF knowledge graph data for [jupyterhub/systemdspawner](https://github.com/jupyterhub/systemdspawner), parsed by [repolex](https://repolex.ai).

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
rlex download jupyterhub/systemdspawner
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 9a0a7f4efe543f50517f84f9985c38269afc77c3
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 9a0a7f4efe543f50517f84f9985c38269afc77c3
│           └── chunk-001.nq.gz
├── blob
│   ├── 08e2c862d18b0e57e16015943ebe4f4d698168f3.nq.gz
│   ├── 0d400e8842f4bb8afe075fafa9ff4e3e3d15c98a.nq.gz
│   ├── 0dc89813dc10ed07777226c26d348a19ce3afb93.nq.gz
│   ├── 154686b80c9c99003a93a039578ed973a6b54476.nq.gz
│   ├── 1e2186e9159c4b570299973615a35581614ec6a8.nq.gz
│   ├── 281b2622665bd1c50a9b0d952c3f643b42820833.nq.gz
│   ├── 28c547738722025e78ca724f64cce2d5a4f2958d.nq.gz
│   ├── 37202a5a79c3229839d5b4dbef28df1ec926a364.nq.gz
│   ├── 39a2f2c69f430fc72f4ab1be9ce7f08c369969d7.nq.gz
│   ├── 528bf32d4637fb2dab42914adaecedbdd7c75cb8.nq.gz
│   ├── 5a5fe86db443150dfd303496e6ad1436de8bc878.nq.gz
│   ├── 6916067663c53df95ad898a0a58b5fd6e8b73fa9.nq.gz
│   ├── 6bb3d33a099107843463e64b8ee720674b35f150.nq.gz
│   ├── 7823bb42c7b7353adf1b56d86a01f548ef06243a.nq.gz
│   ├── 78f0502599662561c571a6f00f4316fe8be7ada7.nq.gz
│   ├── 825c61419ee9e64f838ff5392f1264bb54e1d684.nq.gz
│   ├── 83de00754dca17542d59bdbcdf9c3a5e7b3d1bce.nq.gz
│   ├── 914265064fb45cdb7f0107edab8dadf70845bbf6.nq.gz
│   ├── b055e0d880c73643043d53c1cc5515fa6f20939d.nq.gz
│   ├── e12491a7b7a664a3161b201885c522f36e0d78b9.nq.gz
│   └── ea99ddabfb33212f09229f164b1e14abed2b0b63.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 9a0a7f4efe543f50517f84f9985c38269afc77c3.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 29 files
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

[jupyterhub/systemdspawner](https://github.com/jupyterhub/systemdspawner)

---
*Parsed on 2026-10-15 by [repolex](https://repolex.ai)*
