---
{
  "kind": "primary",
  "routes": {
    "r": "R — entity settings"
  },
  "steps": [
    {
      "text": "The Administrator opens the selected source settings and snippet",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::entity-settings"
        }
      }
    },
    {
      "text": "The selected source exists.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::entity-settings"
        }
      }
    },
    {
      "text": "Source identity, associations, collection overrides, resolved policy, allowed hostnames, filter entries and installation snippet are shown.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "entity",
          "effect": "reads",
          "facts": [
            "Entity ID",
            "Name",
            "Projects",
            "Visitor grouping",
            "Session collection",
            "Campaign collection",
            "Location detail",
            "History retention",
            "Allowed hostnames",
            "Drop rules",
            "Effective collection settings",
            "Custom-data presence",
            "Tracking snippet"
          ]
        },
        {
          "entity": "project",
          "effect": "reads",
          "facts": [
            "Project ID",
            "Name",
            "Visibility",
            "Entities"
          ]
        },
        {
          "entity": "drop-rule",
          "effect": "reads",
          "facts": [
            "Scope",
            "Conditions"
          ]
        }
      ],
      "contexts": {
        "r": {
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
      "target": "crates/liwan/src/app/core/entities.rs"
    }
  ]
}
---

# View Entity settings — settings and snippet

## Trigger

The selected source exists.

## Outcome

Source identity, associations, collection overrides, resolved policy, allowed hostnames, Drop rules and installation snippet are shown.
