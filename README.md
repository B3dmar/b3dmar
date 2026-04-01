# B3dmar

We build infrastructure for AI-augmented knowledge work. Our tools sit between AI providers and the humans who use them, adding the persistence, accountability, and data ownership that frontier models lack.

## Projects

### 3ngram

**The Chief of Staff layer for AI tools.** Persistent memory, structured accountability, and cross-provider context via the Model Context Protocol (MCP).

3ngram connects to Claude, ChatGPT, Cursor, Windsurf, and any MCP-compatible client. It tracks commitments, surfaces blockers, logs decisions with rationale, and sends proactive digests. One memory layer, everywhere.

- **Stack**: FastAPI, PostgreSQL + pgvector, Next.js, MCP (Streamable HTTP + OAuth 2.1)
- **Integrations**: GitHub, Linear, Google Calendar, Basecamp
- **Hosting**: Railway (backend), Vercel (frontend), Neon (database)
- **Docs**: [docs.3ngram.ai](https://docs.3ngram.ai)
- **Product**: [3ngram.ai](https://3ngram.ai)

### Climbr

**Climbing training, data-driven.** A mobile-first app for climbers who want to train with intention. Tracks sessions, analyzes movement patterns, and builds periodized training plans.

- **Stack**: React Native (Expo), Supabase, PostgreSQL
- **Status**: In development

## Philosophy

- **AI should follow through.** Remembering a preference is table stakes. Tracking that you committed to ship something by Friday, then nudging you when it's overdue -- that's the gap we fill.
- **You own your data.** With 3ngram you decide what your AI knows and what it forgets. Move your memory across providers without friction. No vendor lock-in, no opaque training pipelines.
- **Build on labs, not against them.** Frontier models improve every quarter. We integrate into them as infrastructure rather than competing with their conversation layer.

## Team

B3dmar is a one-person company (for now) based in Copenhagen, Denmark. Founded by Sebastian Gade.

## Links

- [3ngram.ai](https://3ngram.ai) -- Product
- [docs.3ngram.ai](https://docs.3ngram.ai) -- Documentation
- [b3dmar.com](https://b3dmar.com) -- Company
