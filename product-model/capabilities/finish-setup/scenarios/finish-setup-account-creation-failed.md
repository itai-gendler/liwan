---
{
  "kind": "edge",
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
      "text": "Valid setup proof reaches identity record creation but storage/creation fails.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "p": {
          "place": "website::public::setup"
        }
      }
    },
    {
      "text": "Failure is returned, no completed setup is promised, and setup availability is retained.",
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

# Finish Setup — account creation failed

## Trigger

Valid setup proof reaches account creation but storage/creation fails.

## Outcome

Failure is returned, no completed setup is promised, and setup availability is retained.
