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
      "text": "Any entry violates supported type, field, property or timestamp validation.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "s": {
          "place": "event-ingestion::server-collection"
        }
      }
    },
    {
      "text": "The complete batch is rejected before queue admission; no partial valid subset is queued. Successful key authentication may already update last use.",
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

# Send event batch — invalid batch

## Trigger

Any entry violates supported type, field, property or timestamp validation.

## Outcome

The complete batch is rejected before queue admission; no partial valid subset is queued. Successful key authentication may already update last use.

## Edge cases

- Acknowledgement is not a persistence receipt; async append errors are separately represented by accepted-write-lost.
