# Architecture Overview

B3dmar builds tools that help knowledge workers stay focused and follow through. This document describes the high-level architecture of our platform.

## System Components

```
┌─────────────┐     ┌──────────────┐     ┌─────────────────┐
│  Web Client  │────▶│   API Layer  │────▶│   PostgreSQL    │
│  (Next.js)   │     │  (FastAPI)   │     │  + pgvector     │
└─────────────┘     └──────┬───────┘     └─────────────────┘
                           │
                    ┌──────▼───────┐     ┌─────────────────┐
                    │  MCP Server  │────▶│  External APIs   │
                    │  (Streamable │     │  (Linear, GH,   │
                    │   HTTP)      │     │   Basecamp)      │
                    └──────────────┘     └─────────────────┘
```

## API Layer

The API is a FastAPI application running on Uvicorn. It handles authentication, CRUD operations, and serves the dashboard. All endpoints require authentication via JWT tokens.

Key design decisions:

- **Row-Level Security (RLS)** enforces user isolation at the database layer
- **pgvector** powers semantic search over user content
- **Async everywhere** via psycopg3 AsyncConnection for non-blocking I/O

## MCP Server

The MCP (Model Context Protocol) server exposes tools that AI assistants can call directly. It runs as a separate process with its own connection pool (sync psycopg3).

## Data Flow

1. User content enters via the API or MCP tools
2. Content is chunked, embedded, and stored in PostgreSQL
3. A background clustering pipeline groups related content
4. Digests and nudges are generated on a cron schedule

## Infrastructure

- **Hosting**: Railway (API, MCP, cron workers)
- **Database**: Railway-managed PostgreSQL 16
- **Frontend**: Vercel (Next.js)
- **DNS**: Cloudflare
