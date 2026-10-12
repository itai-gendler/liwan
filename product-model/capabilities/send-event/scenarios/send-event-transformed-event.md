---
{
  "kind": "primary",
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
      "text": "A configured emission caller transformer receives the normalized payload.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "b": {
          "place": "event-ingestion::public-collection"
        }
      }
    },
    {
      "text": "The Product stores the transformed Pageview using its normalized resulting fields",
      "kind": "product",
      "actor": "tracker",
      "entities": [
        {
          "entity": "pageview",
          "effect": "creates",
          "facts": [
            "Entity ID",
            "Recorded at",
            "Visitor group",
            "Hostname",
            "Path",
            "Referrer",
            "Platform",
            "Browser",
            "Mobile",
            "Country",
            "City",
            "Campaign attribution",
            "Screen width",
            "Orientation",
            "Properties",
            "Pageview timing",
            "Exit time"
          ]
        }
      ],
      "contexts": {
        "b": {
          "place": "event-ingestion::public-collection"
        }
      }
    },
    {
      "text": "The transformer’s resulting valid payload is sent and admitted as its resulting event kind. Defaults merge with per-event overrides; transformer execution follows URL sanitization and can change that payload.",
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

# Send event — transformed event

## Trigger

A configured tracker transformer receives the normalized payload and returns a valid pageview payload.

## Outcome

The transformer’s resulting valid payload is sent and admitted as its resulting event kind. Defaults merge with per-event overrides; transformer execution follows URL sanitization and can change that payload.

## Edge cases

- Acknowledgement is not a persistence receipt; async append errors are separately represented by accepted-write-lost.
- Explicit server-side tracker calls supply endpoint and URL, and the applicable source ID; no browser exit listener runs in that environment.
- A transformed name may produce a Pageview or a custom event. Exits are emitted separately and bypass the transformer.
