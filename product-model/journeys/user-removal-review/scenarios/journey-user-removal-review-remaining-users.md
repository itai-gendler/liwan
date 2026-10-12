---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Website"
  },
  "steps": [
    {
      "text": "The Administrator confirms deletion of the selected identity",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "web": {
          "place": "website::administration::user-settings"
        }
      },
      "capability": "delete-user"
    },
    {
      "text": "Deletion of an existing other identity record is confirmed.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "web": {
          "place": "website::administration::user-settings"
        }
      },
      "capability": "delete-user"
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
        "web": {
          "place": "website::administration::user-settings"
        }
      },
      "capability": "delete-user"
    },
    {
      "text": "The Product carries the caller to the remaining-identity list",
      "kind": "product",
      "actor": "administrator",
      "entities": [],
      "capability": "delete-user",
      "contexts": {
        "web": {
          "place": "website::administration::user-settings"
        }
      }
    },
    {
      "text": "The Administrator requests the identity list",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "web": {
          "place": "website::administration::users"
        }
      },
      "capability": "browse-users"
    },
    {
      "text": "The identity record list is requested.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "web": {
          "place": "website::administration::users"
        }
      },
      "capability": "browse-users"
    },
    {
      "text": "Account usernames and shipped role values are returned without password or external-provider-secret disclosure.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Username",
            "Administrator access"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "website::administration::users"
        }
      },
      "capability": "browse-users"
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
      "target": "crates/liwan/src/cli.rs"
    }
  ]
}
---

# User removal review — remaining users

## Trigger

Remove another account and inspect remaining accounts.

## Outcome

The other account and dependent access are removed and the remaining-account list is read.
