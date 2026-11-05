# MCP Explained

An interactive, animated explainer of the [Model Context Protocol](https://modelcontextprotocol.io): every JSON-RPC message on the wire, step by step.

Live at **https://mcp-explained.com**

- **Start here:** what MCP is, in one definition and one diagram
- **Protocol lessons:** JSON-RPC, lifecycle, transports, authorization, tools, resources, prompts, sampling, elicitation, roots, progress, tasks
- **Spec time machine:** each flow as it worked in 2024-11-05, 2025-03-26, 2025-06-18, 2025-11-25 and 2026-07-28
- **Harness techniques:** tool search and codemode, with and without a gateway
- **Break it:** tool poisoning, tool shadowing, token passthrough, prompt injection, elicitation phishing
- **Coming to MCP:** Skills over MCP, MCP Apps, Server Cards

Every lesson links to the official spec. Corrections welcome: open an issue or a PR.

## How it's built

It's one self-contained HTML file (`public/index.html`): lesson data and the renderer are plain JavaScript, with no build step or dependencies. Open it in a browser to run it locally.

Lessons are objects in the `LESSONS` array. Each has a summary, facts and steps, and each step is a list of messages (`from`, `to`, `kind`, `json`, `notes`). Spec-version differences live in `TM[lessonId][version]`.

It's served as static assets by a Cloudflare Worker (`wrangler.jsonc`):

```sh
npx wrangler dev      # local preview
npx wrangler deploy   # deploy
```

Made by [Runlayer](https://runlayer.com).
