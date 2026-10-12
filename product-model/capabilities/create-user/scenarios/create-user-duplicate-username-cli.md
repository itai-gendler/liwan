---
{
  "kind": "edge",
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
      "text": "The submitted valid name becomes an existing username after Unicode lowercasing.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "c": {
          "place": "liwan-cli"
        }
      }
    },
    {
      "text": "The uniqueness constraint prevents insertion; the CLI reports creation failure and leaves the existing identity record unchanged.",
      "kind": "product",
      "actor": "operator",
      "entities": [],
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

# Create User — duplicate username — cli

## Trigger

The submitted valid name becomes an existing username after Unicode lowercasing.

## Outcome

The uniqueness constraint prevents insertion; the CLI reports creation failure and leaves the existing identity record unchanged.
