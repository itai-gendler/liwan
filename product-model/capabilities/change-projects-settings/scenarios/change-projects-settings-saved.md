---
{
  "kind": "primary",
  "routes": {
    "r": "R — project settings"
  },
  "steps": [
    {
      "text": "The Administrator submits the selected grouping settings",
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
      "text": "A valid name, visibility or display-policy selection is submitted for an existing grouping.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::project-settings"
        }
      }
    },
    {
      "text": "The selected settings are saved without replacing the identifier. Each control’s save is observable; a compound edit is not promised globally atomic.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "project",
          "effect": "changes",
          "facts": [
            "Name",
            "Visibility",
            "Metric display",
            "Dimension display"
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

# Change Projects settings — saved

## Trigger

A valid name, visibility or display-policy selection is submitted for an existing grouping.

## Outcome

The selected settings are saved without replacing the identifier. Each control’s save is observable; a compound edit is not promised globally atomic.
