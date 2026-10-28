# Repolex Knowledge Graph of spatialaudio/sciospecgui

RDF knowledge graph data for [spatialaudio/sciospecgui](https://github.com/spatialaudio/sciospecgui), parsed by [repolex](https://repolex.ai).

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
rlex download spatialaudio/sciospecgui
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── eb73b836062fae85096d25ea728e40b213b4fd86
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── eb73b836062fae85096d25ea728e40b213b4fd86
│           └── chunk-001.nq.gz
├── blob
│   ├── 214989141b0aed8c2cfda9d9ee13a7fe8f09447c.nq.gz
│   ├── 2c8342ae0378bdbe4065fadec4713bdc6648e0d0.nq.gz
│   ├── 857623a9304fd730cd3e3c1ed945b8f706240f1d.nq.gz
│   ├── 98e7a921155314c15f47d124d35423905b04e068.nq.gz
│   ├── a1a918c155ab6b4343c3146cbf84a76fd1aa18de.nq.gz
│   ├── aa9b00fc4cd87d3cb0af6a8d8f49994b5fc7f128.nq.gz
│   ├── e2e434fddb4cb5e764a83167a8f72b3d7fb4e3e3.nq.gz
│   └── f7b07b38197b7c012996f24621e05a99c006622c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── eb73b836062fae85096d25ea728e40b213b4fd86.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 15 files
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

[spatialaudio/sciospecgui](https://github.com/spatialaudio/sciospecgui)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
