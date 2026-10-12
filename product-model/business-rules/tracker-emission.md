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
    }
  ]
}
---

# Tracker emission applies local suppression, payload defaults and the configured transformer

Automatic initial/pathname emission, deduplication, local/opt-out suppression, Navigation API/popstate paths, default-property merge and per-event override; null removes default properties; normalization precedes transformation; exits bypass transformation; explicit server-side events require their configured inputs; no retry guarantee.
