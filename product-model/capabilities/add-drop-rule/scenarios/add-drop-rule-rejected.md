---
{
  "kind": "validation",
  "routes": {
    "r-collection": "R — collection",
    "r-entity-settings": "R — entity settings"
  },
  "steps": [
    {
      "text": "The User adds an empty filter entry to the selected policy",
      "kind": "actor",
      "actor": "user",
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
      "text": "The selected request reaches a refused-entry or missing-session boundary.",
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
      "text": "The request is rejected before protected facts are disclosed or the requested mutation occurs. The underlying subject remains unchanged.",
      "kind": "product",
      "actor": "user",
      "entities": [],
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

# Add Drop rule — rejected

## Trigger

The selected request reaches a refused-entry or missing-session boundary.

## Outcome

The request is rejected before protected facts are disclosed or the requested mutation occurs. The underlying subject remains unchanged.
