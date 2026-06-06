# Retrieval-Augmented Generation

An R demo for the RAG part of deck 03 (Prompt engineering and RAG). It builds a
dynamic RAG system over the "R for Data Science" book with `ragnar`: crawl,
chunk, embed, then expose retrieval as a tool the chat model calls on demand.

## Why this is an instructor demo

RAG needs an embedding model, and Anthropic has no embeddings API. This demo uses
OpenAI embeddings (`embed_openai`) for retrieval while the chat model stays Claude
(`claude-sonnet-4-6`). Workshop participants only have Anthropic set up, so you
run this one.

## Requirements

- R, with `ragnar` and `ellmer` (plus Quarto if you want to render rather than
  run the chunks live).
- `OPENAI_API_KEY` (for the retrieval embeddings) and `ANTHROPIC_API_KEY` (for the
  chat model), read automatically from your `.Renviron`.

## Running

Open `03-rag.qmd` and run the chunks interactively (Positron or RStudio). The
first run crawls and embeds the whole book, so it takes a while; `ragnar`
persists the store to `data/r4ds.ragnar.duckdb`, so later runs reuse it.

## Credit

Adapted from the [posit-conf-2025 LLM workshop](https://github.com/posit-conf-2025/llm/tree/main/_solutions/16_rag); based on the [`ragnar` usage guide](https://ragnar.tidyverse.org/#usage).

## License

MIT License, see the LICENSE file for details.
