---
{
  "kind": "primary",
  "routes": {
    "r-project-settings": "R — project settings",
    "r-entity-settings": "R — entity settings"
  },
  "steps": [
    {
      "text": "The Administrator selects an existing source association for removal",
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
      "text": "A current source association is selected.",
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
      "text": "The association is removed in both directions. Subsequent reports exclude that source’s history; its configuration and event history remain.",
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

# Remove Entity from Project — dissociated

## Trigger

A current source association is selected.

## Outcome

The association is removed in both directions. Subsequent reports exclude that source’s history; its configuration and event history remain.
