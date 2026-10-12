---
{
  "kind": "primary",
  "routes": {
    "r-project-settings": "R — project settings",
    "r-entity-settings": "R — entity settings"
  },
  "steps": [
    {
      "text": "The Administrator selects an existing source to associate with the grouping",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "r-project-settings": {
          "place": "website::administration::project-settings"
        },
        "r-entity-settings": {
          "place": "website::administration::entity-settings"
        }
      }
    },
    {
      "text": "An existing source and grouping are selected.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r-project-settings": {
          "place": "website::administration::project-settings"
        },
        "r-entity-settings": {
          "place": "website::administration::entity-settings"
        }
      }
    },
    {
      "text": "The current association is added in both directions. Subsequent reports include retained history for the newly associated source; no historical event is rewritten.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "entity",
          "effect": "changes",
          "facts": [
            "Projects"
          ]
        },
        {
          "entity": "project",
          "effect": "changes",
          "facts": [
            "Entities"
          ]
        }
      ],
      "contexts": {
        "r-project-settings": {
          "place": "website::administration::project-settings"
        },
        "r-entity-settings": {
          "place": "website::administration::entity-settings"
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

# Add Entity to Project — associated

## Trigger

An existing source and grouping are selected.

## Outcome

The current association is added in both directions. Subsequent reports include retained history for the newly associated source; no historical event is rewritten.
