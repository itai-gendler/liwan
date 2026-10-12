---
{
  "kind": "primary",
  "routes": {
    "r": "R — entity settings"
  },
  "steps": [
    {
      "text": "The Administrator confirms removal of the selected source configuration",
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
      "text": "Deletion of the selected source configuration is confirmed.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::entity-settings"
        }
      }
    },
    {
      "text": "Source configuration, associations and dependent key/membership group source-scope entries are removed. Stored event history remains; reusing the ID can reconnect retained history. The caller is carried to the remaining source list.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "entity",
          "effect": "removes"
        },
        {
          "entity": "project",
          "effect": "changes",
          "facts": [
            "Entities"
          ]
        },
        {
          "entity": "api-key",
          "effect": "changes",
          "facts": [
            "Entities"
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

# Delete Entity — deleted and carried

## Trigger

Deletion of the selected source configuration is confirmed.

## Outcome

Source configuration, associations and dependent key/Team source-scope entries are removed. Stored event history remains; reusing the ID can reconnect retained history. The caller is carried to the remaining source list.
