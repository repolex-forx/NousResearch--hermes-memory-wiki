# Repolex Knowledge Graph of NousResearch/hermes-memory-wiki

RDF knowledge graph data for [NousResearch/hermes-memory-wiki](https://github.com/NousResearch/hermes-memory-wiki), parsed by [repolex](https://repolex.ai).

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
rlex download NousResearch/hermes-memory-wiki
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 9bc3913b8474eaf4d7eec32e97af4d77957c36df
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 9bc3913b8474eaf4d7eec32e97af4d77957c36df.nq.gz
│   └── repolex
│       └── 9bc3913b8474eaf4d7eec32e97af4d77957c36df
│           └── chunk-001.nq.gz
├── blob
│   ├── 0b44a1723b63b4191fbcdc771249600281e4c058.nq.gz
│   ├── 56c48442f8a9607b557385510658809be4aa1ade.nq.gz
│   ├── 5700b997827973cb0eb6d84a2782bb08a5872434.nq.gz
│   ├── 634e16ac5fbac89dcd42832f18c204ab153c7941.nq.gz
│   ├── 6683278808bfa13ebd34062d29f687e973a534b7.nq.gz
│   ├── 68f34a2973acc190795fe84d7a3d364a59434f07.nq.gz
│   ├── 7053c814e0cd7d8971662ba02dd57cd681957a9d.nq.gz
│   ├── 7dba3f3469714c6ebf95c5a1fcb765beda950d74.nq.gz
│   ├── 7efea51d272a395303577f7c65c9aaa510df1000.nq.gz
│   ├── 90efa475e85696a8bd4750ad59386bf4af5f3437.nq.gz
│   ├── a1b6390879441fba247a776b051e71278cacb271.nq.gz
│   ├── a98363fe7065bdd11d028e6f901fb975489d77e0.nq.gz
│   ├── b134b760f5ff0278a004a7ed1b7734c3e511fa6c.nq.gz
│   ├── dc4fa4d1f00c3aec3266621bf87351cfb31d798f.nq.gz
│   └── dd99f72ba4ad537a04a779faf78c08f8e62d52af.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 9bc3913b8474eaf4d7eec32e97af4d77957c36df.nq.gz
├── filetree
│   └── 9bc3913b8474eaf4d7eec32e97af4d77957c36df.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 25 files
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

[NousResearch/hermes-memory-wiki](https://github.com/NousResearch/hermes-memory-wiki)

---
*Parsed on 2026-10-02 by [repolex](https://repolex.ai)*
