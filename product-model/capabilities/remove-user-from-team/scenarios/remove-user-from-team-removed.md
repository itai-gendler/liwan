---
{
  "kind": "primary",
  "routes": {
    "r-user-settings": "R — user settings",
    "r-team-settings": "R — team settings"
  },
  "steps": [
    {
      "text": "The Administrator selects a membership entry to remove",
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
      "text": "A current membership is selected.",
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
      "text": "Membership is removed in both directions; other memberships remain.",
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

# Remove User from Team — removed

## Trigger

A current membership is selected.

## Outcome

Membership is removed in both directions; other memberships remain.
