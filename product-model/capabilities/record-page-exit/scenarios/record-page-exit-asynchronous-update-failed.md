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
      "text": "The exit is acknowledged/queued but delayed update processing fails.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "b": {
          "place": "event-ingestion::public-collection"
        }
      }
    },
    {
      "text": "No completed measurement update is promised; the failure is logged and no later caller rejection or retry guarantee is established.",
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

# Record Pageview exit — asynchronous update failed

## Trigger

The exit is acknowledged/queued but delayed update processing fails.

## Outcome

No completed measurement update is promised; the failure is logged and no later caller rejection or retry guarantee is established.
