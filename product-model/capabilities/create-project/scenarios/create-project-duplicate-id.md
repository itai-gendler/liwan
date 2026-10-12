---
{
  "kind": "edge",
  "routes": {
    "a": "A — project list"
  },
  "steps": [
    {
      "text": "The Administrator supplies a new grouping ID, name and visibility",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "a": {
          "place": "website::account::project-list"
        }
      }
    },
    {
      "text": "The submitted identifier conflicts with an existing subject.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "a": {
          "place": "website::account::project-list"
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

# Create Project — duplicate id

## Trigger

The submitted identifier conflicts with an existing subject.

## Outcome

The create operation reports the conflict and preserves the existing subject; no replacement subject is created.
