---
{
  "kind": "validation",
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
      "text": "Submitted payload fields, URL, client-agent metadata, name or properties violate the implemented validation limits.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "b": {
          "place": "event-ingestion::public-collection"
        }
      }
    },
    {
      "text": "The request is refused before successful persistence of the requested change; no success or hand-off is reported.",
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

# Send event — invalid input

## Trigger

Submitted payload fields, URL, user-agent metadata, name or properties violate the implemented validation limits.

## Outcome

The request is refused before successful persistence of the requested change; no success or hand-off is reported.

## Edge cases

- Acknowledgement is not a persistence receipt; async append errors are separately represented by accepted-write-lost.
