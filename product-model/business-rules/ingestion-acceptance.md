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
    },
    {
      "kind": "doc",
      "role": "context",
      "target": "https://docs.rs/tower_governor/0.8.0/src/tower_governor/governor.rs.html",
      "title": "Pinned rate-limiter replenishment period semantics"
    }
  ]
}
---

# Acknowledgements precede asynchronous persistence and batches reserve only after complete validation

Public filtering acknowledges without storage; keyed batches validate and authorize before whole-batch reservation; accepted/filtered counts; all-scope unknown-source behavior; capacity failures; acknowledgement does not guarantee persistence. The public per-client limit is one replenished request every two seconds with burst ten. Queue reservation is bounded to two seconds. Event/batch capacity failure is 503 with Retry-After: 1, while exits omit that header. Key authentication records last use before later permission/payload rejection. Each batch addresses one source ID and 1–10,000 entries within 10 MiB; no valid subset is queued when whole-batch validation or reservation fails.
