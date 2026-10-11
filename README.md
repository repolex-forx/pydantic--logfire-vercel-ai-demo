# Repolex Knowledge Graph of pydantic/logfire-vercel-ai-demo

RDF knowledge graph data for [pydantic/logfire-vercel-ai-demo](https://github.com/pydantic/logfire-vercel-ai-demo), parsed by [repolex](https://repolex.ai).

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
rlex download pydantic/logfire-vercel-ai-demo
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 0623404cc36e173f18b1760803a1c45143cc724d
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 0623404cc36e173f18b1760803a1c45143cc724d
│           └── chunk-001.nq.gz
├── blob
│   ├── 128e27eec427f9c48afa851fb1847912d4b15036.nq.gz
│   ├── 202dae9ba26f7b8c8634645a576f67f027b3b64d.nq.gz
│   ├── 2121038b845ddc68ca9a647a22e923a4f90862c8.nq.gz
│   ├── 2c1fe3de5b1cff6384d01ad3649434015d035f79.nq.gz
│   ├── 3477cb577326ee465417d0d365c83eb87c1660a9.nq.gz
│   ├── 565ea5627f359a75264dd67d7c71aa9f845a87e4.nq.gz
│   ├── 575285a518bd866eeac4d796167fe3cedc07daf1.nq.gz
│   ├── a814e57bb0214236cd593c042f88ed53972b2e0b.nq.gz
│   ├── b575f7dac742447c79dd92f8b471b7d5e18c32cc.nq.gz
│   ├── dcc87c9cf4c1ca54ed824f7e77b16cc1adc6235d.nq.gz
│   └── e4f5738a310b36b23c51c00b970973de8e79cb17.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 0623404cc36e173f18b1760803a1c45143cc724d.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 17 files
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

[pydantic/logfire-vercel-ai-demo](https://github.com/pydantic/logfire-vercel-ai-demo)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
