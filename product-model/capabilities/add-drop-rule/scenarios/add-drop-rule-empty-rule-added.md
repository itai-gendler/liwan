---
{
  "kind": "primary",
  "routes": {
    "r-collection": "R — collection",
    "r-entity-settings": "R — entity settings"
  },
  "steps": [
    {
      "text": "The Administrator adds an empty filter entry to the selected policy",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "r-collection": {
          "place": "website::administration::collection"
        },
        "r-entity-settings": {
          "place": "website::administration::entity-settings"
        }
      }
    },
    {
      "text": "A global or selected-source filter list is edited.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r-collection": {
          "place": "website::administration::collection"
        },
        "r-entity-settings": {
          "place": "website::administration::entity-settings"
        }
      }
    },
    {
      "text": "One empty filter entry is added to its containing policy. It matches nothing until nonempty conditions are saved.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "drop-rule",
          "effect": "creates",
          "facts": [
            "Scope",
            "Conditions"
          ]
        }
      ],
      "contexts": {
        "r-collection": {
          "place": "website::administration::collection"
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
      "target": "crates/liwan/src/app/core/settings.rs"
    }
  ]
}
---

# Add Drop rule — empty rule added

## Trigger

A global or selected-source filter list is edited.

## Outcome

One empty Drop rule is added to its containing policy. It matches nothing until nonempty conditions are saved.
