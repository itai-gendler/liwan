---
{
  "kind": "primary",
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
      "text": "grouping discovery is requested.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "p": {
          "place": "website::public::projects"
        }
      }
    },
    {
      "text": "The enumerable Project identities, visibility and associated-source metadata are returned. Unlisted direct access does not by itself place a Project in discovery.",
      "kind": "product",
      "actor": "visitor",
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

# Browse Projects — public

## Trigger

Project discovery is requested.

## Outcome

The enumerable Project identities, visibility and associated-source metadata are returned. Unlisted direct access does not by itself place a Project in discovery.
