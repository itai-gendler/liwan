---
{
  "kind": "primary",
  "routes": {
    "a": "A — entity list"
  },
  "steps": [
    {
      "text": "The User opens source discovery",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "a": {
          "place": "website::account::entity-list"
        }
      }
    },
    {
      "text": "Source discovery is requested with a valid sign-in.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "a": {
          "place": "website::account::entity-list"
        }
      }
    },
    {
      "text": "Visible source identities and names are returned with associated Project metadata filtered to enumerable Projects.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "entity",
          "effect": "reads",
          "facts": [
            "Entity ID",
            "Name",
            "Projects"
          ]
        },
        {
          "entity": "project",
          "effect": "reads",
          "facts": [
            "Project ID",
            "Name",
            "Visibility"
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

# Browse Entities — visible entities

## Trigger

Source discovery is requested with a valid sign-in.

## Outcome

Visible source identities and names are returned with associated grouping metadata filtered to enumerable groupings.
