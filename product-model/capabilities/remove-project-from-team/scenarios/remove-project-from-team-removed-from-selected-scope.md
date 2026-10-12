---
{
  "kind": "primary",
  "routes": {
    "r": "R — team settings"
  },
  "steps": [
    {
      "text": "The Administrator removes a selected grouping-access entry",
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
      "text": "A selected grouping-scope entry is removed.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::team-settings"
        }
      }
    },
    {
      "text": "That entry is removed from the Team’s selected grouping scope; its mode and other Teams’ configurations are unchanged.",
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

# Remove Project from Team — removed from selected scope

## Trigger

A selected grouping-scope entry is removed.

## Outcome

That entry is removed from the Team’s selected Project scope; its mode and other Teams’ configurations are unchanged.
