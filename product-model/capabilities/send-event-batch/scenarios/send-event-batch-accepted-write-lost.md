---
{
  "kind": "edge",
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
      "text": "The Product records successful credential authentication before later payload checks or queue admission",
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
    },
    {
      "text": "The batch receives accepted counts and admitted entries are queued, but asynchronous append fails.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "s": {
          "place": "event-ingestion::server-collection"
        }
      }
    },
    {
      "text": "Accepted counts remain the caller’s result while affected history is absent; no later rejection, rollback receipt or retry is promised.",
      "kind": "product",
      "actor": "server-application",
      "entities": [],
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

# Send event batch — accepted write lost

## Trigger

The batch receives accepted counts and admitted entries are queued, but asynchronous append fails.

## Outcome

Accepted counts remain the caller’s result while affected history is absent; no later rejection, rollback receipt or retry is promised.

## Edge cases

- Acknowledgement is not a persistence receipt; async append errors are separately represented by accepted-write-lost.
