---
{
  "kind": "edge",
  "routes": {
    "a": "A — entity list"
  },
  "steps": [
    {
      "text": "The User opens source discovery",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "a": {
          "place": "website::account::entity-list"
        }
      }
    },
    {
      "text": "No subjects are enumerable in the selected context.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "a": {
          "place": "website::account::entity-list"
        }
      }
    },
    {
      "text": "The list is empty, without inventing subjects or disclosing excluded subjects.",
      "kind": "product",
      "actor": "user",
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

# Browse Entities — empty

## Trigger

No subjects are enumerable in the selected context.

## Outcome

The list is empty, without inventing subjects or disclosing excluded subjects.
