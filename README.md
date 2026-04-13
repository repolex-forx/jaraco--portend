# Repolex Knowledge Graph of jaraco/portend

RDF knowledge graph data for [jaraco/portend](https://github.com/jaraco/portend), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download jaraco/portend
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── c0f805a8892f1a46ebfb0a6e8550cfd7104eb542
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── c0f805a8892f1a46ebfb0a6e8550cfd7104eb542.nq.gz
│   └── repolex
│       └── c0f805a8892f1a46ebfb0a6e8550cfd7104eb542
│           └── chunk-001.nq.gz
├── blob
│   ├── 011f5bca8c74597aa83750b9c470e95510d1db2f.nq.gz
│   ├── 14243051409fccc0404edd15a2c993e572626dd8.nq.gz
│   ├── 230b556cbdf7b2cf2e59339f6bf13b6f7ad3e5a4.nq.gz
│   ├── 2e3f4dd791a6372b427d618eb0baa8c4dc58e5f0.nq.gz
│   ├── 304196f81e11a168c9894f966e4a617ebf4ed53c.nq.gz
│   ├── 4d165129ab4b192032398ade75254593a3022364.nq.gz
│   ├── 53513eee9b3a2f4df50df1febd59a5206718995a.nq.gz
│   ├── 54f99acbfac68c2be8283174ea64f1730a795e49.nq.gz
│   ├── 5bdc232005af9be104a00437ae9bc64417a4c1cc.nq.gz
│   ├── 633e3648e99a9faf806677e5a2aabe6036b29f7a.nq.gz
│   ├── 63c0825f6bd49615f4f386b95463111f7992f6bc.nq.gz
│   ├── 6fa480e44f38768722368d7a986607adacf41d99.nq.gz
│   ├── 724370638fc188317bbc7dc868f1a571995fd796.nq.gz
│   ├── 74aa5e146e988601c16fdb95e44b29f813db989d.nq.gz
│   ├── 993895eb8b8f81ddff35d79500d33ff0b09f49e6.nq.gz
│   ├── b2b81eede49917bfa620c0e48e2c0c146faaa20e.nq.gz
│   ├── d226e149623898a43f35ab57295bb82004dc7d8d.nq.gz
│   ├── d9a70bb967c363061170771c00eca73ad8ec7107.nq.gz
│   ├── e1f1998ca4fbc5198d1183f22ba6441f97f4316d.nq.gz
│   └── f6f86bf792d541067095c36c1be00fb62e0fc07b.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── c0f805a8892f1a46ebfb0a6e8550cfd7104eb542.nq.gz
├── filetree
│   └── c0f805a8892f1a46ebfb0a6e8550cfd7104eb542.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 30 files
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

## Source repository

[jaraco/portend](https://github.com/jaraco/portend)

---
*Parsed on 2026-04-13 by [repolex](https://repolex.ai)*
