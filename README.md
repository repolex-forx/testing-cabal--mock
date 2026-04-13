# Repolex Knowledge Graph of testing-cabal/mock

RDF knowledge graph data for [testing-cabal/mock](https://github.com/testing-cabal/mock), parsed by [repolex](https://repolex.ai).

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
lexq download testing-cabal/mock
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── a0d50734eeaa45431845fbf96201e74c56efbe3e
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── a0d50734eeaa45431845fbf96201e74c56efbe3e.nq.gz
│   └── repolex
│       └── a0d50734eeaa45431845fbf96201e74c56efbe3e
│           └── chunk-001.nq.gz
├── blob
│   ├── 0259c2abfdb0060f725d54ae1122fcb4aef21f58.nq.gz
│   ├── 11e0c49cd7abe5fc15042ef78cb08a6d72fd5743.nq.gz
│   ├── 145dc632b312b673deccbd9d7b3966b61fd873cd.nq.gz
│   ├── 1d46ea308604e791887879522ee71dfef4cab39e.nq.gz
│   ├── 2e997059951cc8d85dd76d83324f756472eaad61.nq.gz
│   ├── 3d8d42df906c28f20c14c14e8a4175f7aa7c92fb.nq.gz
│   ├── 3ddd31eea4a6220e318915da6f6f26d60d3bf67e.nq.gz
│   ├── 5ecdb88c004a3b101663d4005eab12b69522201d.nq.gz
│   ├── 6b025eea4c36f2896eb32513c39bbfa4d7e473c2.nq.gz
│   ├── 795caa9b7d97b72ab5516b9b327b39c3308aa7aa.nq.gz
│   ├── 888a7d18a6763a05f5ba1923e70cb560e4561536.nq.gz
│   ├── 9079659183ec3c6bee09bbbf637864791f66610e.nq.gz
│   ├── a15c6c60b0ef212ae4a51386396e845530e2518a.nq.gz
│   ├── a239c55aecab5b5ea898c9cd0b60d32a3fd31180.nq.gz
│   ├── b2fbf6b2aa8c1e1509d19b6d81fea6c3e6bd8782.nq.gz
│   ├── bee7e5fd61d115eee69a4e36e2b61661e5f4b12c.nq.gz
│   ├── c9e6fd10b1379a38d25fb8991f5488f82a763b70.nq.gz
│   ├── cde205fc6b7ee86292b5c7aafbc60bf7afb7ffb3.nq.gz
│   ├── d2d7f6faedbbca809e427636fb8dc40909ae7dba.nq.gz
│   ├── f2de9d69127c03e35d7701c0511a2bde0f6442a7.nq.gz
│   ├── fbaf7843cf8fb0cf7d389219e2ee98c249e6c222.nq.gz
│   └── fea73d9e0cf2b8a4c9b69e80e7a926013b69fb5c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── a0d50734eeaa45431845fbf96201e74c56efbe3e.nq.gz
├── filetree
│   └── a0d50734eeaa45431845fbf96201e74c56efbe3e.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 32 files
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

[testing-cabal/mock](https://github.com/testing-cabal/mock)

---
*Parsed on 2026-04-13 by [repolex](https://repolex.ai)*
