# Repolex Knowledge Graph of click-contrib/click-completion

RDF knowledge graph data for [click-contrib/click-completion](https://github.com/click-contrib/click-completion), parsed by [repolex](https://repolex.ai).

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
rlex download click-contrib/click-completion
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 39e8b5453ee2a816b9fd86c563eeecc59060f7af
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 39e8b5453ee2a816b9fd86c563eeecc59060f7af
│           └── chunk-001.nq.gz
├── blob
│   ├── 08aedd7e61b9921f0a7844c3826bda5c611bc5e2.nq.gz
│   ├── 0b5f182b7ed91a5f190e5f5f1b8d4ce4cfed8c9d.nq.gz
│   ├── 15dd29db453afe5aa9696abcc6457aebae77de18.nq.gz
│   ├── 186a67fa712f22d80c498ae15c487ad59106a10a.nq.gz
│   ├── 2a0e85afed01c22ab84b8b505b9d7bcd52c5dd25.nq.gz
│   ├── 3a7a8f12fa00acb89fe51a502f20f7ce34f84278.nq.gz
│   ├── 4bda58f77a1dbc00962b83e1357776fad86fc5dd.nq.gz
│   ├── 63b0b638e871c1ed86cc69abfe0fa65eac1b8d04.nq.gz
│   ├── 6fc093f43ab59a9346ae5bd2ef722e93ccb9676b.nq.gz
│   ├── 8250279c77d74a665e8600124ef280c4b7222104.nq.gz
│   ├── a8d052ed7cf8ccf0a18a0ad41835062e4f623093.nq.gz
│   ├── b94054ecdea2ff305d06ef07d7b8fa58116b21f8.nq.gz
│   ├── bd012682a9e161273c4b815b396cf18e27cf7e08.nq.gz
│   ├── d1073bb7247bb51ff897804560fa0debdcb6e8d7.nq.gz
│   ├── dc51e734174e29c6203d13faabc803782b8bd97e.nq.gz
│   ├── e2d07d9ae690cebd59c5f8b469e2d3b10ec1ad6f.nq.gz
│   ├── ebd9c3ab983cb00b567cf781b653a9da71333d0e.nq.gz
│   ├── f23c7f2ab70583ef6f1fe4ca232111a8a65495b1.nq.gz
│   ├── f33e5d9dbdf7583b8c6f7c938773fdc17953dd33.nq.gz
│   └── f605ed12a9a8d5731be4039c7a983ebbfc60d351.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 39e8b5453ee2a816b9fd86c563eeecc59060f7af.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 28 files
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

[click-contrib/click-completion](https://github.com/click-contrib/click-completion)

---
*Parsed on 2026-10-18 by [repolex](https://repolex.ai)*
