---
{
  "type": "api",
  "actors": [
    "tracker",
    "server-application"
  ],
  "entryPoints": [
    {
      "api": "/api/event"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/web/routes/event.rs"
    }
  ]
}
---

# Event ingestion

Trackers submit individual events and exits; server applications submit API-key-authenticated batches.
