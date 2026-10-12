---
{
  "kind": "primary",
  "routes": {
    "r-collection": "R — collection",
    "r-entity-settings": "R — entity settings"
  },
  "steps": [
    {
      "text": "The Administrator submits the selected rule’s condition values",
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
      "text": "A rule’s supported condition entries are changed.",
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
      "text": "The rule’s conditions are replaced. Conditions within the rule combine with AND; any matching global or source rule drops an event.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "drop-rule",
          "effect": "changes",
          "facts": [
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

# Edit Drop rule — conditions changed

## Trigger

A rule’s supported condition entries are changed.

## Outcome

The rule’s conditions are replaced. Conditions within the rule combine with AND; any matching global or source rule drops an event.
