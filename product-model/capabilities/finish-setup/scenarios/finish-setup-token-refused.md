---
{
  "kind": "validation",
  "routes": {
    "p": "P — setup"
  },
  "steps": [
    {
      "text": "The Visitor supplies the setup token, username and new password",
      "kind": "actor",
      "actor": "visitor",
      "entities": [],
      "contexts": {
        "p": {
          "place": "website::public::setup"
        }
      }
    },
    {
      "text": "Setup is unavailable or token proof does not match.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "p": {
          "place": "website::public::setup"
        }
      }
    },
    {
      "text": "Setup is rejected without creating an identity record, consuming available setup or issuing a session.",
      "kind": "product",
      "actor": "visitor",
      "entities": [],
      "contexts": {
        "p": {
          "place": "website::public::setup"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/web/routes/auth.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/web/session.rs"
    }
  ]
}
---

# Finish Setup — token refused

## Trigger

Setup is unavailable or token proof does not match.

## Outcome

Setup is rejected without creating an account, consuming available setup or issuing a session.
