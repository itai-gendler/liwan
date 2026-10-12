---
{
  "kind": "validation",
  "routes": {
    "a": "A — project list"
  },
  "steps": [
    {
      "text": "The User supplies a new grouping ID, name and visibility",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "a": {
          "place": "website::account::project-list"
        }
      }
    },
    {
      "text": "A valid dashboard session resolves to the ordinary role when this administration request is attempted.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "a": {
          "place": "website::account::project-list"
        }
      }
    },
    {
      "text": "The request returns Forbidden (403) before protected settings are disclosed or the requested administrative operation is performed.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "a": {
          "place": "website::account::project-list"
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
      "target": "crates/liwan/src/app/core/projects.rs"
    }
  ]
}
---

# Create Project — access rejected

## Trigger

A valid dashboard session resolves to the ordinary User role when this administration request is attempted.

## Outcome

The request returns Forbidden (403) before protected settings are disclosed or the requested administrative operation is performed.

## Edge cases

- A missing or invalid dashboard session returns Unauthorized (401) before this operation; malformed browser credential pairs are cleared.
