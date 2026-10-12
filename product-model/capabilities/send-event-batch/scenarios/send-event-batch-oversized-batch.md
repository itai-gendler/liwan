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
      "text": "A successfully authenticated request has an otherwise valid body with more than 10,000 entries.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "s": {
          "place": "event-ingestion::server-collection"
        }
      }
    },
    {
      "text": "The request returns 413 without queue admission; successful authentication has already recorded last use",
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

# Send event batch — oversized batch

## Trigger

A successfully authenticated request has an otherwise valid body with more than 10,000 entries.

## Outcome

The request returns 413 without queue admission; successful authentication has already recorded last use.

## Edge cases

- Bodies exceeding 10 MiB are also rejected by the body limit; empty batches return 400. Authentication failure takes precedence when credential extraction fails.

- Acknowledgement is not a persistence receipt; async append errors are separately represented by accepted-write-lost.
