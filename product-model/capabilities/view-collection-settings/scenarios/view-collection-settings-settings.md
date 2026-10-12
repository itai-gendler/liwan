---
{
  "kind": "primary",
  "routes": {
    "r": "R — collection"
  },
  "steps": [
    {
      "text": "The Administrator opens the global collection policy",
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
      "text": "Global global collection policy are requested.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::collection"
        }
      }
    },
    {
      "text": "Current global grouping policy, session/campaign collection, location detail, retention and filter entries are shown.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "collection-settings",
          "effect": "reads",
          "facts": [
            "Visitor grouping",
            "Session collection",
            "Campaign collection",
            "Location detail",
            "History retention",
            "Drop rules"
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

# View Collection settings — settings

## Trigger

Global collection settings are requested.

## Outcome

Current global visitor grouping, session/campaign collection, location detail, retention and Drop rules are shown.
