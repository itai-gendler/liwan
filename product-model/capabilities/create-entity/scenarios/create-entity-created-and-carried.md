---
{
  "kind": "primary",
  "routes": {
    "a": "A — entity list"
  },
  "steps": [
    {
      "text": "The Administrator supplies a new source ID and name",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "a": {
          "place": "website::account::entity-list"
        }
      }
    },
    {
      "text": "A new valid source ID and name are submitted.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "a": {
          "place": "website::account::entity-list"
        }
      }
    },
    {
      "text": "The source is created with empty grouping associations, inheriting collection defaults and an empty allowed-host list, and the caller is carried to its settings/snippet editor.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "entity",
          "effect": "creates",
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
            "Drop rules"
          ]
        }
      ],
      "contexts": {
        "a": {
          "place": "website::account::entity-list"
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

# Create Entity — created and carried

## Trigger

A new valid source ID and name are submitted.

## Outcome

The source is created with empty grouping associations, inheriting collection defaults and an empty allowed-host list, and the caller is carried to its settings/snippet editor.

## Edge cases

- The Website submits no initial grouping associations. Source overrides start inherited; hostname filtering starts with an empty list.
