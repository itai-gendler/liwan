---
{
  "kind": "primary",
  "routes": {
    "r": "R — users"
  },
  "steps": [
    {
      "text": "The Administrator requests the identity list",
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
      "text": "The identity record list is requested.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::users"
        }
      }
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

# Browse Users — website list

## Trigger

The account list is requested.

## Outcome

Account usernames and Administrator-access values are returned without password or external-provider-secret disclosure.
