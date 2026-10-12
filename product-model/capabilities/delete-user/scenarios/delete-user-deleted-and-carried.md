---
{
  "kind": "primary",
  "routes": {
    "r": "R — user settings"
  },
  "steps": [
    {
      "text": "The Administrator confirms deletion of the selected identity",
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
      "text": "Deletion of an existing other identity record is confirmed.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::user-settings"
        }
      }
    },
    {
      "text": "The Account and its dependent sessions/memberships are removed and the caller is carried to the remaining-Account list.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "account",
          "effect": "removes"
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

# Delete User — deleted and carried

## Trigger

Deletion of an existing other account is confirmed.

## Outcome

The account and its dependent sessions/memberships are removed and the caller is carried to the remaining-account list.


## Edge cases

- The handler compares the requested name with the caller’s stored name using ASCII case-insensitivity before the service uses Unicode lowercasing. A retained caller name `äa` and requested name `Äa` do not match that guard, yet deletion selects `äa`; its sessions and memberships are removed along with the account. This is a requested-name endpoint boundary: Website controls use the stored name and intercept own deletion before making a request. A successful endpoint response does not preserve the deleted caller’s sign-ins.
