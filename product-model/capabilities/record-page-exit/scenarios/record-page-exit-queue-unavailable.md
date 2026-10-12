---
{
  "kind": "edge",
  "routes": {
    "b": "B"
  },
  "steps": [
    {
      "text": "The Tracker submits the latest tracked page’s exit signal",
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
      "text": "Queue reservation cannot complete within the implemented capacity window.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "b": {
          "place": "event-ingestion::public-collection"
        }
      }
    },
    {
      "text": "Capacity failure returns 503 without queuing the rejected entries. Event/batch reservation uses Retry-After: 1; exit reservation does not promise that header.",
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

# Record Pageview exit — queue unavailable

## Trigger

Queue reservation cannot complete within the implemented capacity window.

## Outcome

Capacity failure returns 503 without queuing the rejected entries. Event/batch reservation uses Retry-After: 1; exit reservation does not promise that header.
