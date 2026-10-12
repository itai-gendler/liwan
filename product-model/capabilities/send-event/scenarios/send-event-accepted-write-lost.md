---
{
  "kind": "edge",
  "routes": {
    "b": "B"
  },
  "steps": [
    {
      "text": "The Tracker emits the individual occurrence payload using the configured emission caller inputs",
      "kind": "actor",
      "actor": "tracker",
      "entities": [],
      "contexts": {
        "b": {
          "place": "event-ingestion::public-collection"
        }
      }
    },
    {
      "text": "A request is acknowledged and queued but asynchronous event append fails.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "b": {
          "place": "event-ingestion::public-collection"
        }
      }
    },
    {
      "text": "The caller retains the successful acknowledgement while the event is absent from persisted reports; failure is logged without a later rejection or promised retry.",
      "kind": "product",
      "actor": "tracker",
      "entities": [],
      "contexts": {
        "b": {
          "place": "event-ingestion::public-collection"
        }
      }
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

# Send event — accepted write lost

## Trigger

A request is acknowledged and queued but asynchronous event append fails.

## Outcome

The caller retains the successful acknowledgement while the event is absent from persisted reports; failure is logged without a later rejection or promised retry.

## Edge cases

- Acknowledgement is not a persistence receipt; async append errors are separately represented by accepted-write-lost.
