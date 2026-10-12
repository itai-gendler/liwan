---
{
  "kind": "edge",
  "routes": {
    "a": "A — entity list"
  },
  "steps": [
    {
      "text": "The Administrator supplies a new source ID and name",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "a": {
          "place": "website::account::entity-list"
        }
      }
    },
    {
      "text": "The submitted identifier conflicts with an existing subject.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "a": {
          "place": "website::account::entity-list"
        }
      }
    },
    {
      "text": "The create operation reports the conflict and preserves the existing subject; no replacement subject is created.",
      "kind": "product",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "a": {
          "place": "website::account::entity-list"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/web/routes/admin.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/entities.rs"
    }
  ]
}
---

# Create Entity — duplicate id

## Trigger

The submitted identifier conflicts with an existing subject.

## Outcome

The create operation reports the conflict and preserves the existing subject; no replacement subject is created.
