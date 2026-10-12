---
{
  "kind": "primary",
  "routes": {
    "c": "C"
  },
  "steps": [
    {
      "text": "The Operator requests the identity list",
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
      "text": "The identity record list is requested.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "c": {
          "place": "liwan-cli"
        }
      }
    },
    {
      "text": "Account usernames and shipped role values are returned without password or external-provider-secret disclosure.",
      "kind": "product",
      "actor": "operator",
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

# Browse Users — cli list

## Trigger

The account list is requested.

## Outcome

Account usernames and Administrator-access values are returned without password or external-provider-secret disclosure.
