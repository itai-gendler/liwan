---
{
  "kind": "primary",
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
      "text": "No eligible match exists, or session collection is disabled, grouping is random or required metadata is absent.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "b": {
          "place": "event-ingestion::public-collection"
        }
      }
    },
    {
      "text": "The exit is acknowledged without changing a measurement or creating a counted event.",
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

# Record Pageview exit — ignored exit

## Trigger

No eligible match exists, or session collection is disabled, grouping is random or required metadata is absent.

## Outcome

The exit is acknowledged without changing a measurement or creating a counted event.
