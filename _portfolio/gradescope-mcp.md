---
title: "gradescope-mcp"
excerpt: "An MCP server with 74 tools that lets AI assistants work through real Gradescope grading: assignments, rubrics, submissions, extensions and regrade requests. Writes to Gradescope return a preview first and run only on an explicit confirmation, which the agent is told to get from a person."
collection: portfolio
order: 3
github: "https://github.com/Yuanpeng-Li/gradescope-mcp"
---

[`gradescope-mcp`](https://github.com/Yuanpeng-Li/gradescope-mcp) is an open-source [MCP](https://modelcontextprotocol.io/) server that exposes 74 tools spanning course, assignment, rubric, submission, roster, extension, and regrade-request management on [Gradescope](https://www.gradescope.com/).

Designed for instructors and TAs who want AI agents to drive real grading workflows while keeping a human firmly in the loop, every write operation follows a `preview-first` pattern: tools return a preview when `confirm_write=False` and only execute after explicit confirmation. The repo also ships a reusable local skill for human-approved batch grading.

Built and maintained by me as a natural outgrowth of TAing five UCI Statistics courses.
