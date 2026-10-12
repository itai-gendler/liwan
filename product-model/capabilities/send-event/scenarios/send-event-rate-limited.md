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
      "text": "The shared public per-client throttle is exceeded.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "b": {
          "place": "event-ingestion::public-collection"
        }
      }
    },
    {
      "text": "A rate-limit response (429) is returned without queuing the rejected signal.",
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

# Send event — rate limited

## Trigger

The shared public per-client throttle is exceeded.

## Outcome

A rate-limit response (429) is returned without queuing the rejected signal.

## Edge cases

- Acknowledgement is not a persistence receipt; async append errors are separately represented by accepted-write-lost.
