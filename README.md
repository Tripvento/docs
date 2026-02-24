# Tripvento Docs (Mintlify Experiment)

This repo is an experiment. The canonical Tripvento API documentation lives at [tripvento.com/docs](https://tripvento.com/docs) — built with Next.js, maintained by hand, and deployed alongside the main site. That's the source of truth.

This Mintlify site is a mirror we're using to answer a simple question: **can Claude Code maintain a low-stakes documentation project on its own?**

## What Tripvento does

[Tripvento](https://tripvento.com) is an intent-based hotel ranking API. Instead of sorting hotels by stars or price, we score every property across 14 travel intents — romantic, family, nightlife, wellness, business, and more — using a combination of geospatial, semantic, and sentiment signals. The API powers hotel recommendations for travel platforms, AI assistants (via MCP), and internal tools.

- **[tripvento.com](https://tripvento.com)** — Main website
- **[tripvento.com/pricing](https://tripvento.com/pricing)** — Plans and API keys (Sandbox is free)
- **[tripvento.com/about](https://tripvento.com/about)** — Our story
- **[tripvento.com/docs](https://tripvento.com/docs)** — Primary documentation

## Why this repo exists

We use AI heavily in how our product works — LLMs score hotels, analyze reviews, and generate reasoning. But we write our own code. The application, the API, the ranking engine — that's human-built.

Documentation is different. It's structured, repetitive, and needs to stay in sync with a source of truth that already exists. It's the kind of work where an AI agent can genuinely be useful without the risks that come with letting it touch production code.

So this is the experiment: point Claude Code at the Next.js docs page, tell it to keep this Mintlify site in sync, and see how far it gets. Low stakes, high signal. If it works well, we learn something about where AI agents fit in a real workflow. If it doesn't, we've lost nothing — the real docs are untouched.

The Mintlify site also runs on its own subdomain, which gives us DR90+ backlinks to tripvento.com for free. That's a nice side effect.

## What's in here

```
docs.json              # Mintlify configuration (nav, theme, links)
index.mdx              # Introduction
quickstart.mdx         # Get your first API response in 2 minutes
authentication.mdx     # API key setup
intents.mdx            # All 14 travel intents
thin-mode.mdx          # Smaller payloads for faster responses
caching.mdx            # Cache-Control headers and best practices
rate-limits.mdx        # Monthly quotas and burst limits by tier
errors.mdx             # Error codes and response format
mcp-integration.mdx    # MCP setup for Claude, Cursor, etc.
api-reference/
  endpoints.mdx        # Full endpoint reference
```

## Local development

```bash
npm i -g mint
mint dev
```

Preview at `http://localhost:3000`.

## Deployment

Pushes to the default branch deploy automatically via the Mintlify GitHub app.
