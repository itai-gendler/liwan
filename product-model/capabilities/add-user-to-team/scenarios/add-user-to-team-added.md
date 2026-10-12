---
{
  "kind": "primary",
  "routes": {
    "r-user-settings": "R — user settings",
    "r-team-settings": "R — team settings"
  },
  "steps": [
    {
      "text": "The Administrator selects an identity to add to the membership group",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "r-user-settings": {
          "place": "website::administration::user-settings"
        },
        "r-team-settings": {
          "place": "website::administration::team-settings"
        }
      }
    },
    {
      "text": "An existing identity record and membership group are selected.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r-user-settings": {
          "place": "website::administration::user-settings"
        },
        "r-team-settings": {
          "place": "website::administration::team-settings"
        }
      }
    },
    {
      "text": "Membership is added in both directions; the saved Account Teams and Team Members agree.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Teams"
          ]
        },
        {
          "entity": "team",
          "effect": "changes",
          "facts": [
            "Members"
          ]
        }
      ],
      "contexts": {
        "r-user-settings": {
          "place": "website::administration::user-settings"
        },
        "r-team-settings": {
          "place": "website::administration::team-settings"
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
      "target": "crates/liwan/src/app/core/users.rs"
    }
  ]
}
---

# Add User to Team — added

## Trigger

An existing account and Team are selected.

## Outcome

Membership is added in both directions; the saved Account Teams and Team Members agree.
