# Repolex Knowledge Graph of astral-sh/multiplay

RDF knowledge graph data for [astral-sh/multiplay](https://github.com/astral-sh/multiplay), parsed by [repolex](https://repolex.ai).

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
rlex download astral-sh/multiplay
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ff7ced1bb3d2ca3c0a2ab1740e4426eff4f9cd33
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ff7ced1bb3d2ca3c0a2ab1740e4426eff4f9cd33
│           └── chunk-001.nq.gz
├── blob
│   ├── 1475a4b9fe63deffa6fa6f564686ceff45a11323.nq.gz
│   ├── 351663b181b68e2b88173bd86cdedfecda955a25.nq.gz
│   ├── 3a52d7f122416bcd0afcc16fc27f023826f0a973.nq.gz
│   ├── 46ea8d04bccbe31ccdd4338cb5097c7dcf611122.nq.gz
│   ├── 494d87f70ddc9c1cc56115eacff48e08e475d91c.nq.gz
│   ├── 505a3b1ca2716907d5b292ab90c36df043c42bb6.nq.gz
│   ├── 5a63018d805619904e2cd07b25383e44a84e4161.nq.gz
│   ├── 6324d401a069f4020efcf0ff07442724b52f47c2.nq.gz
│   ├── 659abefa0ff7b643557328be18b2ce4e421bc21a.nq.gz
│   ├── 6a3d6a3ce96a629610411af6b47186b39bccdcc0.nq.gz
│   ├── 7ca0b98cac4fc49d1382dc23cb0cfa9a7dd5a485.nq.gz
│   ├── 7ebc680fd160cb6702098883e1bfffb21d448126.nq.gz
│   ├── 87f454affbc78da250945d3024c9d3260b899437.nq.gz
│   ├── 8c66ff454270eaac11b4f5c34dfb5d399a230e27.nq.gz
│   ├── 991e840b80c24cb0ce67da79a6a31f2b1a5b3a32.nq.gz
│   ├── 9e311905df9993f472f876028b46c26ae595e163.nq.gz
│   └── b405fa3a9597cb2de17097b7f8e5dde8f9baac78.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ff7ced1bb3d2ca3c0a2ab1740e4426eff4f9cd33.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 24 files
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

[astral-sh/multiplay](https://github.com/astral-sh/multiplay)

---
*Parsed on 2026-10-10 by [repolex](https://repolex.ai)*
