# Repolex Knowledge Graph of dtolnay/proc-macro-hack

RDF knowledge graph data for [dtolnay/proc-macro-hack](https://github.com/dtolnay/proc-macro-hack), parsed by [repolex](https://repolex.ai).

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
rlex download dtolnay/proc-macro-hack
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── fe0889cb7a67adfe070fad449066034e7a662f56
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── fe0889cb7a67adfe070fad449066034e7a662f56.nq.gz
│   └── repolex
│       └── fe0889cb7a67adfe070fad449066034e7a662f56
│           └── chunk-001.nq.gz
├── blob
│   ├── 01dbc0d58f3a9f9b781f12e6e00083d6c95e9ffb.nq.gz
│   ├── 0a8a6750f1665e941eb1d4db0401a04df1ccb4ac.nq.gz
│   ├── 122ded5191f58ae6f0f93a718de5742771129ad9.nq.gz
│   ├── 127a36c946290627a43f845c77405d9c80f799ec.nq.gz
│   ├── 16fe87b06e802f094b3fbb0894b137bca2b16ef1.nq.gz
│   ├── 1ab84446c7e6f4b00d9172515d9f483c31d9f12a.nq.gz
│   ├── 1dfa83b03364040b776b743070bf6b19fd147334.nq.gz
│   ├── 376fc0d9866bfc19514e5d5cf7974bf3bd1a6420.nq.gz
│   ├── 3d30690f120489337cb61685b2f0f0d45af983c1.nq.gz
│   ├── 50f81c115aba33b94f9f543f939650a51b49d307.nq.gz
│   ├── 54c2db9e5fcdffeb0b4032645101b6025f785a59.nq.gz
│   ├── 603101690228756a83683ed1863adc1dfee85fb1.nq.gz
│   ├── 60761b5149f0d4b03f6cd42f6d6f298e2e121a8e.nq.gz
│   ├── 6ab40985b60bc2f8b39559409735c4eaf25f36be.nq.gz
│   ├── 722013c7d6c05f6fd481f05f48317b7962f7a2a0.nq.gz
│   ├── 7334a53d9a9bc0606b7282def05cc26d73aefe16.nq.gz
│   ├── 750707701cdae985156601cc906195021ba6a6e5.nq.gz
│   ├── 76219eb72e8524f15c21ec93b9b2592da49b5460.nq.gz
│   ├── 772e6673d053de2a597fcbcfab257f804dc6c1a3.nq.gz
│   ├── 7e8b88e14e1b5f547f2036c416c52b1c93572ce2.nq.gz
│   ├── 80b2a41bd1f4bd58e0e2bf875c81e94e4e4cccbd.nq.gz
│   ├── 965b606f331b51d566b46025f9ff311a7aad0c12.nq.gz
│   ├── 9a5a8ac4326b40fccdf62411e8e857d219cbbf48.nq.gz
│   ├── a3d648d1a499e62639cf15369998a465354f9b47.nq.gz
│   ├── a9d37c560c6ab8d4afbf47eda643e8c42e857716.nq.gz
│   ├── aa9b82c8f4ce7795a1ecc472e489dca581337539.nq.gz
│   ├── b72b8ef9dd6f289743bc1a70cfc66d8c0731d082.nq.gz
│   ├── d3a3ea7ed4d4365f00b355a3f858952ab4e20866.nq.gz
│   ├── e9ad4f3ddde643b950eac4c89af79f1f6dcf3854.nq.gz
│   ├── f2675cdf1ea42fc674ebdd71c501d955cf88ec57.nq.gz
│   ├── f32f05a1cd70ae5767aa83cfb365a9b0b270fed9.nq.gz
│   ├── f37c8f9e21b78565193b1d9099980bd7c0c2a577.nq.gz
│   ├── f9aea23b5154721f04537b60075baf789f06e6ba.nq.gz
│   └── f9c3b80290452538cd6907173d6a840eb14333e2.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── fe0889cb7a67adfe070fad449066034e7a662f56.nq.gz
├── filetree
│   └── fe0889cb7a67adfe070fad449066034e7a662f56.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 44 files
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

[dtolnay/proc-macro-hack](https://github.com/dtolnay/proc-macro-hack)

---
*Parsed on 2026-11-22 by [repolex](https://repolex.ai)*
