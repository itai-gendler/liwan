---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "custom-event",
      "effect": "creates",
      "contexts": [
        {
          "place": "event-ingestion::server-collection"
        }
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "server-application"
      ],
      "configuredBy": "api-key"
    }
  ],
  "references": [
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

# Server applications create custom events only within their authenticated API Key’s configured batch scope

The configuredBy API Key is the successfully authenticated credential for this request. It must carry events:batch and include this request’s exact source ID in direct scope or the union of currently scoped Projects’ Entity associations. All direct scope includes unregistered IDs; unrelated keys never qualify. Authorization precedes whole-batch reservation and is not rechecked at later persistence.
