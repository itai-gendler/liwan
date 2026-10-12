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
      "text": "The acting identity record is selected for all-device revocation.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::user-settings"
        }
      }
    },
    {
      "text": "Its sign-ins are revoked, browser credentials cleared and the caller carried to sign-in; credentials are unchanged.",
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

# Revoke sessions — own account and carried

## Trigger

The acting account is selected for all-device revocation.

## Outcome

Its sign-ins are revoked, browser credentials cleared and the caller carried to sign-in; credentials are unchanged.
