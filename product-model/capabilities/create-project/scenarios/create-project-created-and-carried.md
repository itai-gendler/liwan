---
{
  "kind": "primary",
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
      "text": "A new valid grouping ID, name and visibility are submitted.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "a": {
          "place": "website::account::project-list"
        }
      }
    },
    {
      "text": "The Project is created with empty source associations and default display settings, and the caller is carried to its settings editor.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "project",
          "effect": "creates",
          "facts": [
            "Project ID",
            "Name",
            "Visibility",
            "Entities",
            "Metric display",
            "Dimension display"
          ]
        }
      ],
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

# Create Project — created and carried

## Trigger

A new valid grouping ID, name and visibility are submitted.

## Outcome

The grouping is created with empty source associations and default display settings, and the caller is carried to its settings editor.

## Edge cases

- The Website submits no initial source associations. The selected visibility defaults to Private; existing IDs are never renamed by settings edits.
