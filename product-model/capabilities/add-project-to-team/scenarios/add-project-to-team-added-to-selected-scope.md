---
{
  "kind": "primary",
  "routes": {
    "r": "R — team settings"
  },
  "steps": [
    {
      "text": "The Administrator adds an existing grouping to selected access scope",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::team-settings"
        }
      }
    },
    {
      "text": "An existing grouping is selected under selected grouping scope.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::team-settings"
        }
      }
    },
    {
      "text": "The selected grouping ID is added to the Team’s saved selected grouping scope.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "team",
          "effect": "changes",
          "facts": [
            "Projects"
          ]
        }
      ],
      "contexts": {
        "r": {
          "place": "website::administration::team-settings"
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
      "target": "crates/liwan/src/app/core/teams.rs"
    }
  ]
}
---

# Add Project to Team — added to selected scope

## Trigger

An existing grouping is selected under selected Project scope.

## Outcome

The selected Project ID is added to the Team’s saved selected Project scope.
