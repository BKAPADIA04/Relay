# Relay

A Corrective Retrieval-Augmented Generation (Corrective RAG / CRAG) system.

## Overview

Standard RAG pipelines blindly trust whatever the retriever returns, which means
irrelevant or low-quality documents can end up feeding the generator and
degrading answer quality. Relay addresses this by grading retrieved documents
before generation and taking a corrective action based on that grade:

- **Correct** — retrieved documents are relevant; refine and pass them to the generator.
- **Ambiguous / Incorrect** — retrieved documents are irrelevant or insufficient;
  fall back to an alternative retrieval strategy (e.g. web search or query rewriting)
  before generation.

## Planned Pipeline

1. **Retrieve** — fetch candidate documents for a query from the vector store.
2. **Grade** — score each document's relevance to the query.
3. **Correct** — based on the grade, either refine the retrieved context or
   trigger a fallback retrieval (query rewrite, web search, etc.).
4. **Generate** — produce the final answer using the corrected context.

## Status

This project is in early development. Architecture and implementation details
will be fleshed out as the system is built.

## Reference

- Yan, S.-Q., Gu, J.-C., Zhu, Y., & Ling, Z.-H. (2024). [Corrective Retrieval Augmented Generation](https://arxiv.org/pdf/2401.15884). arXiv:2401.15884.
