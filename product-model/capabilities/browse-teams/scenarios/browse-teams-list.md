---
{
  "kind": "primary",
  "routes": {
    "r": "R — teams"
  },
  "steps": [
    {
      "text": "The Administrator requests the membership-group list",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::teams"
        }
      }
    },
    {
      "text": "The membership group list is requested.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::teams"
        }
      }
    },
    {
      "text": "Team identities, names and member counts are returned.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "team",
          "effect": "reads",
          "facts": [
            "Team ID",
            "Name",
            "Members"
          ]
        }
      ],
      "contexts": {
        "r": {
          "place": "website::administration::teams"
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
      "target": "crates/liwan/src/app/core/teams.rs"
    }
  ]
}
---

# Browse Teams — list

## Trigger

The Team list is requested.

## Outcome

Team identities, names and member counts are returned.
