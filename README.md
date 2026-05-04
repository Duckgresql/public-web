# Duckgresql — Public Website

Source for the **Duckgresql** public site: [duckgresql.cloud](https://duckgresql.cloud).

## What is Duckgresql?

**Duckgresql is DuckDB for real applications** — DuckDB's analytical engine, made operable for apps with concurrent users.

It's delivered as:

- A **remote service** that handles the operational layer: connection pooling, memory configuration per connection, query routing under concurrent load, and graceful error handling.
- A **DuckDB-compatible Python SDK**. Replace `import duckdb` with `import duckgresql`, point it at the remote service, and keep using the same execution methods (`fetchall`, `fetchone`, `fetchdf`, `fetch_arrow_table`, async support).

```python
import duckgresql

conn = duckgresql.connect(token="dkgql_...", database="my_database")
result = conn.execute(
    "SELECT user_id, COUNT(*) FROM events GROUP BY 1"
).fetchall()
```

A **Postgres bridge** is available as an optional capability for teams migrating from Postgres or wanting to query both systems with one SQL surface. It's not in the hot path.

## What's in the SDK today

- DuckDB-compatible Python API (connect, execute, fetch methods, async support).
- Concurrent reads against tuned DuckDB engines.
- Async jobs for long-running analytical queries.
- Optional Postgres bridge for gradual migration or unified queries.

JavaScript / TypeScript SDK is on the way.

## Status

Private beta. We're taking on **five teams as design partners**: free during the program, direct access to the founder, in exchange for a 30-minute call every two weeks. We prioritize teams already running DuckDB in or near production.

Apply at [duckgresql.cloud#apply](https://duckgresql.cloud#apply).

## About this repo

This repository contains only the static landing site (`index.html`, `privacy.html`, `terms.html`) deployed at `duckgresql.cloud`. The product itself lives elsewhere.

---

© 2026 Duckgresql. All rights reserved.
