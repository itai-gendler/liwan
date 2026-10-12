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
      "text": "Queue reservation cannot complete within the implemented capacity window.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "s": {
          "place": "event-ingestion::server-collection"
        }
      }
    },
    {
      "text": "Capacity failure returns 503 without queuing the rejected entries. Event/batch reservation uses Retry-After: 1; exit reservation does not promise that header.",
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

# Send event batch — queue unavailable

## Trigger

Queue reservation cannot complete within the implemented capacity window.

## Outcome

Capacity failure returns 503 without queuing the rejected entries. Event/batch reservation uses Retry-After: 1; exit reservation does not promise that header.

## Edge cases

- Acknowledgement is not a persistence receipt; async append errors are separately represented by accepted-write-lost.
