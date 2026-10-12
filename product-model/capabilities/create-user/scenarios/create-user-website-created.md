---
{
  "kind": "primary",
  "routes": {
    "r": "R — users"
  },
  "steps": [
    {
      "text": "The Administrator supplies username, password and the selected shipped role",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::users"
        }
      }
    },
    {
      "text": "An unused valid username and supplied password are submitted with the selected shipped role.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::users"
        }
      }
    },
    {
      "text": "A local Account is created with hashed password verification, chosen administrative role access, empty initial membership group memberships and no automatically issued sign-in. Website creation completes on the Account-list process.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "account",
          "effect": "creates",
          "facts": [
            "Username",
            "Administrator access",
            "Local credential",
            "External identity",
            "Teams",
            "Sign-ins"
          ]
        }
      ],
      "contexts": {
        "r": {
          "place": "website::administration::users"
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
      "target": "crates/liwan/src/cli.rs"
    }
  ]
}
---

# Create User — website created

## Trigger

An unused valid username and supplied password are submitted with the selected shipped role.

## Outcome

A local account is created with hashed password verification, chosen Administrator access, empty initial Team memberships and no automatically issued sign-in. Website creation completes on the account-list process.
