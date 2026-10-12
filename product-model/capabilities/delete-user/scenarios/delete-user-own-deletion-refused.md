---
{
  "kind": "validation",
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
      "text": "The requested target-name spelling matches the acting identity’s stored username under ASCII case-insensitive comparison.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::user-settings"
        }
      }
    },
    {
      "text": "Own deletion is refused (403), leaving the identity record and its dependencies intact.",
      "kind": "product",
      "actor": "administrator",
      "entities": [],
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "packages/web/src/components/settings/users/index.tsx"
    }
  ]
}
---

# Delete User — own deletion refused

## Trigger

The requested target-name spelling matches the acting account’s stored username under ASCII case-insensitive comparison.

## Outcome

Own deletion is refused (403), leaving the account and its dependencies intact.


## Edge cases

- For the stored own-account name, Website controls show the own-account deletion refusal without sending a deletion request; the ASCII-matching handler request is independently refused with 403.
