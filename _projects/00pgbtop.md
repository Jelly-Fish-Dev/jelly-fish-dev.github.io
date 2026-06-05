---
title: pgbtop
awards: Open Source · Python · Typescript · PostgreSQL · Apache 2.0
description: A btop-style live terminal and web monitor for PostgreSQL, streaming real-time query, lock, and session data over WebSocket to a Textual TUI or web client.
hackathon: https://github.com/Jelly-Fish-Dev/pgbtop
date: 2026-06-01
layout: project
---

A btop-style live monitor for PostgreSQL. It streams real-time data from PostgreSQL system tables to connected clients over WebSocket, designed to run on the database host and be accessed remotely via SSH tunnel.

### What it monitors

- **Active queries** — live sessions from `pg_stat_activity`
- **Slow queries** — aggregated history from `pg_stat_statements`
- **Locks** — blocking detection from `pg_locks`

### Architecture

The stack is split into two components:

| Component | Stack |
|---|---|
| `pgbtop-server` | Node.js WebSocket server — polls PostgreSQL and broadcasts JSON |
| `pgbtop-client` | Python + [Textual](https://textual.textualize.io/) — runs as a terminal UI or served as a web app |

The server binds to `localhost` by default. The recommended access pattern is an SSH tunnel — no public port exposure required:

```
your machine  ──SSH tunnel──►  database host  ──localhost──►  pgbtop-server
```

Clients authenticate with a shared token. TLS is used for WebSocket transport; in production, forward the port over SSH rather than exposing it directly.
