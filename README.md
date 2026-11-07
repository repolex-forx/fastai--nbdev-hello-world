# Repolex Knowledge Graph of fastai/nbdev-hello-world

RDF knowledge graph data for [fastai/nbdev-hello-world](https://github.com/fastai/nbdev-hello-world), parsed by [repolex](https://repolex.ai).

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
rlex download fastai/nbdev-hello-world
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── da3c08d0ffcc9e1744a4fc0b5ceffa741a912dc8
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── da3c08d0ffcc9e1744a4fc0b5ceffa741a912dc8
│           └── chunk-001.nq.gz
├── blob
│   ├── 0a6dfcb2f20aeeb3b9b36e44d534c646114dc302.nq.gz
│   ├── 23926d531870596b1947435d2cfbc338621bdeae.nq.gz
│   ├── 3b106e87c0610102b42d042be9c79bc967c84503.nq.gz
│   ├── 56085923ac597c0618c5b3a9d710487ed4eef03c.nq.gz
│   ├── 5c0e7ced193cb35aee60cbadc3e022a1da0fd8cc.nq.gz
│   ├── 5f112e28c3a6dc6f8e7df0d6edce550d5bcc474d.nq.gz
│   ├── 631e561feb0d1af7c629a588e5e0e5cc1f7406fa.nq.gz
│   ├── 6552cc5da9d5ec82c8562804039b51283739ae48.nq.gz
│   ├── 6671b7136caeebf6c0e1b14a5cda881d181a5333.nq.gz
│   ├── 66ccc49ee8f0e73901dac02dc4e9224b7d1b2c78.nq.gz
│   ├── 68a7b319e1465d97bab28b03e8e0b66439f8ee4c.nq.gz
│   ├── acb24ac803bafae9c7ea6e28a8dc9af3c7365d00.nq.gz
│   ├── b1411d10d3859c5b0a996e1ea0d3a14dc0d49e41.nq.gz
│   ├── cd6d7dfb5f2bab2af1dcd4c2423bb5a853cd525b.nq.gz
│   ├── e3281ae9bd7b98568e77014dba1b7b353d409205.nq.gz
│   └── f102a9cadfa89ce554b3b26d2b90bfba2e05273c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── da3c08d0ffcc9e1744a4fc0b5ceffa741a912dc8.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 23 files
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

[fastai/nbdev-hello-world](https://github.com/fastai/nbdev-hello-world)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
