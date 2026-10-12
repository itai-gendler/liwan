---
{
  "kind": "primary",
  "routes": {
    "r": "R — user settings"
  },
  "steps": [
    {
      "text": "The Administrator opens the selected identity’s settings",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::user-settings"
        }
      }
    },
    {
      "text": "The selected identity record exists.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::user-settings"
        }
      }
    },
    {
      "text": "Its username, administrative role access and current Teams are shown, together with the all-device session-revocation operation; no inventory of individual sessions is promised.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Username",
            "Administrator access",
            "Teams"
          ]
        },
        {
          "entity": "team",
          "effect": "reads",
          "facts": [
            "Team ID",
            "Name"
          ]
        }
      ],
      "contexts": {
        "r": {
          "place": "website::administration::user-settings"
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

# View User settings — selected user

## Trigger

The selected account exists.

## Outcome

Its username, Administrator access and current Teams are shown, together with the all-device session-revocation operation; no inventory of individual sessions is promised.
