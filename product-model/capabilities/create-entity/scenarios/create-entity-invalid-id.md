---
{
  "kind": "validation",
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
      "text": "The submitted identifier violates the implemented creation/form constraints.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "a": {
          "place": "website::account::entity-list"
        }
      }
    },
    {
      "text": "The request is refused before successful persistence of the requested change; no success or hand-off is reported.",
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

# Create Entity — invalid id

## Trigger

The submitted identifier violates the implemented creation/form constraints.

## Outcome

The request is refused before successful persistence of the requested change; no success or hand-off is reported.
