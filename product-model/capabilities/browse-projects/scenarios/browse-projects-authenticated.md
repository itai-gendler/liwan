---
{
  "kind": "primary",
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
      "text": "grouping discovery is requested.",
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
      "text": "The enumerable Project identities, visibility and associated-source metadata are returned. Unlisted direct access does not by itself place a Project in discovery.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "project",
          "effect": "reads",
          "facts": [
            "Project ID",
            "Name",
            "Visibility",
            "Entities"
          ]
        }
      ],
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

# Browse Projects — authenticated

## Trigger

Project discovery is requested.

## Outcome

The enumerable Project identities, visibility and associated-source metadata are returned. Unlisted direct access does not by itself place a Project in discovery.
