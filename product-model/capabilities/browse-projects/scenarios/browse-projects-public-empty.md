---
{
  "kind": "edge",
  "routes": {
    "p": "P — projects"
  },
  "steps": [
    {
      "text": "The Visitor opens discovery with the selected metric and range",
      "kind": "actor",
      "actor": "visitor",
      "entities": [],
      "contexts": {
        "p": {
          "place": "website::public::projects"
        }
      }
    },
    {
      "text": "No subjects are enumerable in the selected context.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "p": {
          "place": "website::public::projects"
        }
      }
    },
    {
      "text": "The list is empty, without inventing subjects or disclosing excluded subjects.",
      "kind": "product",
      "actor": "visitor",
      "entities": [],
      "contexts": {
        "p": {
          "place": "website::public::projects"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/web/routes/dashboard.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/projects.rs"
    }
  ]
}
---

# Browse Projects — public empty

## Trigger

No subjects are enumerable in the selected context.

## Outcome

The list is empty, without inventing subjects or disclosing excluded subjects.
