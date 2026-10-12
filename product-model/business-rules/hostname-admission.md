---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "send-event",
      "contexts": [
        {
          "place": "event-ingestion::public-collection"
        }
      ]
    },
    {
      "type": "capability",
      "id": "send-event-batch",
      "contexts": [
        {
          "place": "event-ingestion::server-collection"
        }
      ]
    },
    {
      "type": "capability",
      "id": "record-page-exit",
      "contexts": [
        {
          "place": "event-ingestion::public-collection"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/web/routes/event.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/events.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "packages/tracker/src/script.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/web/routes/v1.rs:60"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/api_keys.rs"
    }
  ]
}
---

# Allowed hostnames match the submitted URL host and an empty list admits all

Empty list admits all; normalized exact/wildcard patterns inspect submitted URL host; `*.` admits subdomains, not apex; no browser-Origin ownership verification.
