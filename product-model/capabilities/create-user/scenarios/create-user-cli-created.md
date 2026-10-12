---
{
  "kind": "primary",
  "routes": {
    "c": "C"
  },
  "steps": [
    {
      "text": "The Operator supplies username, password and the selected shipped role",
      "kind": "actor",
      "actor": "operator",
      "entities": [],
      "contexts": {
        "c": {
          "place": "liwan-cli"
        }
      }
    },
    {
      "text": "An unused valid username and supplied password are submitted with the selected shipped role.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "c": {
          "place": "liwan-cli"
        }
      }
    },
    {
      "text": "A local Account is created with hashed password verification, chosen administrative role access, empty initial membership group memberships and no automatically issued sign-in. Website creation completes on the Account-list process.",
      "kind": "product",
      "actor": "operator",
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
        "c": {
          "place": "liwan-cli"
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

# Create User — cli created

## Trigger

An unused valid username and supplied password are submitted with the selected shipped role.

## Outcome

A local account is created with hashed password verification, chosen Administrator access, empty initial Team memberships and no automatically issued sign-in.
