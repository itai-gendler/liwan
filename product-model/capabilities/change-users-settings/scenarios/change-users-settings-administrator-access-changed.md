---
{
  "kind": "primary",
  "routes": {
    "r": "R — user settings"
  },
  "steps": [
    {
      "text": "The Administrator submits a changed role value for the selected identity",
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
      "text": "An existing other identity record is selected and its administrative role-access value is changed.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::user-settings"
        }
      }
    },
    {
      "text": "The selected Account’s administrative role access is saved and subsequent session requests resolve the current role.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Administrator access"
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

# Change Users settings — administrator access changed

## Trigger

An existing other account is selected and its Administrator-access value is changed.

## Outcome

The selected account’s Administrator access is saved and subsequent session requests resolve the current role.
