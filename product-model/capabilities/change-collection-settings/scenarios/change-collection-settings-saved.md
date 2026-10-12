---
{
  "kind": "primary",
  "routes": {
    "r": "R — collection"
  },
  "steps": [
    {
      "text": "The Administrator submits the selected global collection values",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::collection"
        }
      }
    },
    {
      "text": "Valid global policy values are submitted.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::collection"
        }
      }
    },
    {
      "text": "Global defaults are saved. Sources inheriting each edited setting resolve the new default for subsequent collection; historical clearing requires explicit pruning.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "collection-settings",
          "effect": "changes",
          "facts": [
            "Visitor grouping",
            "Session collection",
            "Campaign collection",
            "Location detail",
            "History retention"
          ]
        }
      ],
      "contexts": {
        "r": {
          "place": "website::administration::collection"
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
      "target": "crates/liwan/src/app/core/settings.rs"
    }
  ]
}
---

# Change Collection settings — saved

## Trigger

Valid global collection settings are submitted.

## Outcome

Global defaults are saved. Sources inheriting each edited setting resolve the new default for subsequent collection; historical clearing requires explicit pruning.
