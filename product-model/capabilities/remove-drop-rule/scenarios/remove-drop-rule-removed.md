---
{
  "kind": "primary",
  "routes": {
    "r-collection": "R — collection",
    "r-entity-settings": "R — entity settings"
  },
  "steps": [
    {
      "text": "The Administrator removes the selected filter entry",
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
      "text": "An existing rule is selected for removal.",
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
      "text": "The rule is removed from its containing policy; remaining rules continue to accumulate.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "drop-rule",
          "effect": "removes"
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

# Remove Drop rule — removed

## Trigger

An existing rule is selected for removal.

## Outcome

The rule is removed from its containing policy; remaining rules continue to accumulate.
