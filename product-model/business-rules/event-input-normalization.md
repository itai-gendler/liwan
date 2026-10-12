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

# Collection validates input bounds and preserves submitted identifiers and event names

Source IDs and event names must be nonblank after checking whitespace and at most 255 UTF-8 bytes; their submitted spelling is retained without trimming. URL, referrer, user-agent and screen/orientation metadata are bounded to 2,048, 256, 1,024 and 20 bytes respectively. Property keys are trimmed and limited to 1–64 Unicode characters; values are limited to 255 Unicode characters. Null and empty string values are omitted, numbers and booleans become strings, and arrays or objects are refused. At most 30 normalized property entries remain; collisions after key trimming share one entry. Stored paths omit query and fragment, while recognized campaign attribution is retained separately. Batch timestamps accept RFC3339, default to receipt time, and reject more than five minutes in the future; there is no corresponding oldest-timestamp bound.
