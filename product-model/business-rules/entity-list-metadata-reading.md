---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "entity",
      "effect": "reads",
      "facts": [
        "Entity ID",
        "Name",
        "Projects"
      ],
      "contexts": [
        {
          "place": "website::account::entity-list"
        }
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "administrator"
      ]
    },
    {
      "actors": [
        "user"
      ],
      "configuredBy": "project"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/utils/validate.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/web/routes/dashboard.rs"
    }
  ]
}
---

# Administrators or Users with an enumerable associated Project discover Entity metadata

An Administrator discovers all Entity metadata. A User requires at least one currently associated Project enumerable by that acting Account. Returned Project associations are filtered to enumerable Projects; the Entity-read permission vocabulary is not an independent source-discovery grant.
