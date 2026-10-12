---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Website"
  },
  "steps": [
    {
      "text": "The Administrator supplies a new grouping ID, name and visibility",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "web": {
          "place": "website::account::project-list"
        }
      },
      "capability": "create-project"
    },
    {
      "text": "A new valid grouping ID, name and visibility are submitted.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "web": {
          "place": "website::account::project-list"
        }
      },
      "capability": "create-project"
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
        "web": {
          "place": "website::account::project-list"
        }
      },
      "capability": "create-project"
    },
    {
      "text": "The Product carries the caller to the new grouping editor",
      "kind": "product",
      "actor": "administrator",
      "entities": [],
      "capability": "create-project",
      "contexts": {
        "web": {
          "place": "website::account::project-list"
        }
      }
    },
    {
      "text": "The Administrator opens the selected grouping editor",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "web": {
          "place": "website::administration::project-settings"
        }
      },
      "capability": "view-project-settings"
    },
    {
      "text": "The selected grouping exists.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "web": {
          "place": "website::administration::project-settings"
        }
      },
      "capability": "view-project-settings"
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
        "web": {
          "place": "website::administration::project-settings"
        }
      },
      "capability": "view-project-settings"
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

# Project onboarding — project editor

## Trigger

Create a grouping and reach its editor.

## Outcome

The new grouping exists and its current settings have been read.
