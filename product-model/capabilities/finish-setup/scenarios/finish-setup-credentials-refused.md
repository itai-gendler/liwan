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
      "text": "Submitted setup credentials violate the applicable form or handler constraints.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "p": {
          "place": "website::public::setup"
        }
      }
    },
    {
      "text": "Credential validation fails before identity record creation; setup remains available when it was available.",
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

# Finish Setup — credentials refused

## Trigger

Submitted setup credentials violate the applicable form or handler constraints.

## Outcome

Credential validation fails before account creation; setup remains available when it was available.
