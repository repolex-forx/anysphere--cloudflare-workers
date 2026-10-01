# Repolex Knowledge Graph of anysphere/cloudflare-workers

RDF knowledge graph data for [anysphere/cloudflare-workers](https://github.com/anysphere/cloudflare-workers), parsed by [repolex](https://repolex.ai).

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
rlex download anysphere/cloudflare-workers
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 393c4c95467ae9932d16da3ee1b9a8cf141209a1
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 393c4c95467ae9932d16da3ee1b9a8cf141209a1.nq.gz
│   └── repolex
│       └── 393c4c95467ae9932d16da3ee1b9a8cf141209a1
│           └── chunk-001.nq.gz
├── blob
│   ├── 061604126603bde2441d686bd697c74a6ddbc3c1.nq.gz
│   ├── 09359a9e53b1576fdf917381ec8d460840731108.nq.gz
│   ├── 09b9f850cae33a7b5f817a8076bd6776c6e4a0e0.nq.gz
│   ├── 10ea298d93598617ccb11f83f0470da9c4353a1f.nq.gz
│   ├── 305725b57f23032abe0eee3bd89e1c08c29b684e.nq.gz
│   ├── 31ea443a54cd1b347ab9cda72655a3131d5d727a.nq.gz
│   ├── 5926ebd3ab732ed67ccabc3ad00b91793e62ed03.nq.gz
│   ├── 59767418daa0efe06425ee010f630c247ead8d22.nq.gz
│   ├── 5c7ad3d69d8a4068313d6cef34075ce7f2cc6d48.nq.gz
│   ├── 6e145bec4f19c90120c90a7f52080f0c65a9667d.nq.gz
│   ├── 7650cb0203512b532f9d9873fa7059e578b8280d.nq.gz
│   ├── 8b5840acac7af00022dc5e1797e1ee64c69c745d.nq.gz
│   ├── 900fec12dd97480147dbca94bd6e1597a77a3317.nq.gz
│   ├── 9e59fa412fd96c1efec78ed1ddc0dae652ccaa24.nq.gz
│   ├── a54a3f1cf29c28234b2d066350ad5861f38f2361.nq.gz
│   ├── b0f9dc940d7dca83e5f2d6f6050e43de3b67122e.nq.gz
│   ├── b7509ef13adbddab70d2882131a7594f043263d7.nq.gz
│   ├── f0f7a9d0726957422adcb27cc4b743482e771841.nq.gz
│   └── f9f23e95a435d76c810c0d8d9d959a13fb8cbd27.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 393c4c95467ae9932d16da3ee1b9a8cf141209a1.nq.gz
├── filetree
│   └── 393c4c95467ae9932d16da3ee1b9a8cf141209a1.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 28 files
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

[anysphere/cloudflare-workers](https://github.com/anysphere/cloudflare-workers)

---
*Parsed on 2026-10-01 by [repolex](https://repolex.ai)*
