---
{
  "kind": "primary",
  "routes": {
    "r": "R — user settings"
  },
  "steps": [
    {
      "text": "The Administrator requests all-device sign-in revocation for the selected identity",
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
      "text": "Session revocation is requested for the selected identity record.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::user-settings"
        }
      }
    },
    {
      "text": "All of its dashboard sign-ins are revoked without changing credentials. Other Accounts’ sessions are unaffected.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Sign-ins"
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

# Revoke sessions — other account

## Trigger

Session revocation is requested for the selected account.

## Outcome

All of its dashboard sign-ins are revoked without changing credentials. Other accounts’ sessions are unaffected.
