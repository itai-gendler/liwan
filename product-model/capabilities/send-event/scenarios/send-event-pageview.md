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
      "text": "A valid unfiltered page occurrence is emitted, automatically on initial/pathname tracking or by an explicit call.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "b": {
          "place": "event-ingestion::public-collection"
        }
      }
    },
    {
      "text": "Public acknowledgement precedes asynchronous admission/persistence. An admitted Pageview is stored with normalized attribution/properties and applicable Pageview timing.",
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

# Send event — pageview

## Trigger

A valid unfiltered pageview is emitted, automatically on initial/pathname tracking or by an explicit call.

## Outcome

Public acknowledgement precedes asynchronous admission/persistence. An admitted Pageview is stored with normalized attribution/properties and applicable Pageview timing.

## Edge cases

- Acknowledgement is not a persistence receipt; async append errors are separately represented by accepted-write-lost.
- Explicit server-side tracker calls supply endpoint and URL, and the applicable source ID; no browser exit listener runs in that environment.
