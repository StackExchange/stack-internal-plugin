---
name: search
description: Search Stack Internal when the user asks about their organization's knowledge, policies, technical decisions, or documentation, or explicitly asks to look something up in Stack Internal.
---

Use the connected Stack Internal MCP server to answer the user's question.

1. Search for the user's topic with `search_nodes`. Start with a clear phrase, then narrow or change terms if the results are too broad or miss the likely terminology.
2. Retrieve the most relevant results with `get_node`, using node IDs from the search results. Read the available text and metadata, including dates, classification, and trust information when present.
3. Answer from the retrieved nodes and link to their original sources when the server provides URLs. If no URL is available, identify the source by title and node ID. Distinguish source facts from your own inference, and call out stale or conflicting guidance.
4. If the connection fails or the sources do not answer the question, say so plainly. Do not invent internal facts.
