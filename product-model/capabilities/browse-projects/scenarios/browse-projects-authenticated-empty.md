---
{
  "kind": "edge",
  "routes": {
    "a-projects": "A — projects",
    "a-project-list": "A — project list"
  },
  "steps": [
    {
      "text": "The User opens discovery with the selected metric and range",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "a-projects": {
          "place": "website::account::projects"
        },
        "a-project-list": {
          "place": "website::account::project-list"
        }
      }
    },
    {
      "text": "No subjects are enumerable in the selected context.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "a-projects": {
          "place": "website::account::projects"
        },
        "a-project-list": {
          "place": "website::account::project-list"
        }
      }
    },
    {
      "text": "The list is empty, without inventing subjects or disclosing excluded subjects.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "a-projects": {
          "place": "website::account::projects"
        },
        "a-project-list": {
          "place": "website::account::project-list"
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

# Browse Projects — authenticated empty

## Trigger

No subjects are enumerable in the selected context.

## Outcome

The list is empty, without inventing subjects or disclosing excluded subjects.
