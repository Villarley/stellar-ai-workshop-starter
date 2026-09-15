---
name: stellar-research
description: Research a Stellar ecosystem project, protocol, or topic using Raven and save a short cited findings report. Use when asked to look into a Stellar project, protocol, SCF proposal, or ecosystem topic.
---

# Stellar Research

Use the Raven MCP tool to answer a question about a Stellar project, protocol, or ecosystem topic, then save the findings as a file the user can commit.

## Steps

1. If the user hasn't named a topic, ask for one: a project name, a protocol, or a subject like "RWA tokenization on Stellar" or "Soroban oracles."
2. Call `mcp__raven__search` with a query built from that topic to find the relevant operations or skills (for example `scout.searchProjects`, `lumenloop.search_content_semantic`, `stellarDocs.search_docs`, `scout.searchResearch`).
3. Call `mcp__raven__execute` with one script that runs the relevant operations from the search results (use `Promise.all` for independent calls) and returns cited rows.
4. Write the findings to `research/<topic-slug>.md`: a short summary (5-10 bullet points), each citing its source URL and date. State clearly if a result is unverified or inconclusive rather than guessing.
5. Tell the user the file is ready to review, then commit and push it.

## Notes

- Keep the report short. This is a 20-minute workshop exercise, not a deep research pass.
- Prefer Raven's own citations over general knowledge - the point of the exercise is showing live ecosystem data, not a summary from memory.
