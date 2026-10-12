---
{
  "kind": "primary",
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
      "text": "A valid batch contains admitted page occurrences within effective key scope.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "s": {
          "place": "event-ingestion::server-collection"
        }
      }
    },
    {
      "text": "Whole-batch validation and scope checks precede reservation. Accepted/filtered counts are returned; admitted Pageviews are asynchronously stored with applicable timing.",
      "kind": "product",
      "actor": "server-application",
      "entities": [
        {
          "entity": "api-key",
          "effect": "changes",
          "facts": [
            "Last used at"
          ]
        },
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

# Send event batch — pageviews

## Trigger

A valid batch contains admitted pageviews within effective key scope.

## Outcome

Whole-batch validation and scope checks precede reservation. Accepted/filtered counts are returned; admitted Pageviews are asynchronously stored with applicable timing.

## Edge cases

- Acknowledgement is not a persistence receipt; async append errors are separately represented by accepted-write-lost.
