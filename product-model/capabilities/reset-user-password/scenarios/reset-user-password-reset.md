---
{
  "kind": "primary",
  "routes": {
    "c": "C"
  },
  "steps": [
    {
      "text": "The Operator supplies a replacement password for the selected identity",
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
      "text": "The selected identity record exists and a replacement password is supplied to the CLI.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "c": {
          "place": "liwan-cli"
        }
      }
    },
    {
      "text": "The local credential is replaced and dashboard sessions are revoked without old-password proof or a Website session. The CLI does not impose the Website’s eight-character minimum.",
      "kind": "product",
      "actor": "operator",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Local credential",
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

# Reset User password — reset

## Trigger

The selected account exists and a replacement password is supplied to the CLI.

## Outcome

The local credential is replaced and dashboard sessions are revoked without old-password proof or a Website session. The CLI does not impose the Website’s eight-character minimum.
