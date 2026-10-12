---
{
  "kind": "validation",
  "routes": {
    "s": "S"
  },
  "steps": [
    {
      "text": "The submitting application submits the single-source batch and its credential",
      "kind": "actor",
      "actor": "server-application",
      "entities": [],
      "contexts": {
        "s": {
          "place": "event-ingestion::server-collection"
        }
      }
    },
    {
      "text": "A successfully authenticated key lacks supported batch permission or any requested source is outside effective direct/grouping scope.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "s": {
          "place": "event-ingestion::server-collection"
        }
      }
    },
    {
      "text": "The batch is rejected (403) before reservation. Last use already records authentication; no permission recheck at later persistence is promised.",
      "kind": "product",
      "actor": "server-application",
      "entities": [
        {
          "entity": "api-key",
          "effect": "changes",
          "facts": [
            "Last used at"
          ]
        }
      ],
      "contexts": {
        "s": {
          "place": "event-ingestion::server-collection"
        }
      }
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
      "target": "crates/liwan/src/app/core/events.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/api_keys.rs"
    }
  ]
}
---

# Send event batch — scope refused

## Trigger

A successfully authenticated key lacks supported batch permission or the requested source is outside effective direct/Project scope.

## Outcome

The batch is rejected (403) before reservation. Last use already records authentication; no permission recheck at later persistence is promised.

## Edge cases

- Acknowledgement is not a persistence receipt; async append errors are separately represented by accepted-write-lost.
- The request has one source ID shared by every entry; current Project-following membership is resolved before reservation, while authentication has already recorded last use.
