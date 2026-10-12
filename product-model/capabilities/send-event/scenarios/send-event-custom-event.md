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
      "text": "A valid named occurrence is explicitly emitted.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "b": {
          "place": "event-ingestion::public-collection"
        }
      }
    },
    {
      "text": "Public acknowledgement precedes asynchronous admitted-event storage with normalized attribution/properties; no page occurrence timing is created for the named occurrence.",
      "kind": "product",
      "actor": "tracker",
      "entities": [
        {
          "entity": "custom-event",
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
            "Event name"
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

# Send event — custom event

## Trigger

A valid named custom event is explicitly emitted.

## Outcome

Public acknowledgement precedes asynchronous admitted-event storage with normalized attribution/properties; no Pageview timing is created for the custom event.

## Edge cases

- Acknowledgement is not a persistence receipt; async append errors are separately represented by accepted-write-lost.
- Explicit server-side tracker calls supply endpoint and URL, and the applicable source ID; no browser exit listener runs in that environment.
