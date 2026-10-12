---
{
  "kind": "primary",
  "routes": {
    "r": "R — project settings"
  },
  "steps": [
    {
      "text": "The Administrator confirms deletion of the selected grouping",
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
      "text": "Deletion of the selected existing grouping is confirmed.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::project-settings"
        }
      }
    },
    {
      "text": "The Project, configuration and dependent access-scope references are removed; source configuration and event history remain. The caller is carried to the remaining Project list.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "project",
          "effect": "removes"
        },
        {
          "entity": "entity",
          "effect": "changes",
          "facts": [
            "Projects"
          ]
        },
        {
          "entity": "team",
          "effect": "changes",
          "facts": [
            "Projects"
          ]
        },
        {
          "entity": "api-key",
          "effect": "changes",
          "facts": [
            "Projects"
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

# Delete Project — deleted and carried

## Trigger

Deletion of the selected existing grouping is confirmed.

## Outcome

The grouping, configuration and dependent access-scope references are removed; source configuration and event history remain. The caller is carried to the remaining grouping list.
