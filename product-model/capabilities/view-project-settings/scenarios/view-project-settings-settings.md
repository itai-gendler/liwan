---
{
  "kind": "primary",
  "routes": {
    "r": "R — project settings"
  },
  "steps": [
    {
      "text": "The Administrator opens the selected grouping editor",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::project-settings"
        }
      }
    },
    {
      "text": "The selected grouping exists.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::project-settings"
        }
      }
    },
    {
      "text": "Identity, visibility, current source associations and metric/dimension display settings are shown.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "project",
          "effect": "reads",
          "facts": [
            "Project ID",
            "Name",
            "Visibility",
            "Entities",
            "Metric display",
            "Dimension display"
          ]
        },
        {
          "entity": "entity",
          "effect": "reads",
          "facts": [
            "Entity ID",
            "Name"
          ]
        }
      ],
      "contexts": {
        "r": {
          "place": "website::administration::project-settings"
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

# View Project settings — settings

## Trigger

The selected grouping exists.

## Outcome

Identity, visibility, current source associations and metric/dimension display settings are shown.
