---
{
  "kind": "primary",
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
      "text": "No identity record existed at startup and initial setup remains available. A valid token and valid new credentials are submitted.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "p": {
          "place": "website::public::setup"
        }
      }
    },
    {
      "text": "The first administrative role Account is created, setup availability is consumed, and the installer is carried to sign-in without receiving a dashboard session.",
      "kind": "product",
      "actor": "visitor",
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
        },
        {
          "entity": "installation-settings",
          "effect": "changes",
          "facts": [
            "Setup availability"
          ]
        }
      ],
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

# Finish Setup — complete

## Trigger

No account existed at startup and initial setup remains available. A valid token and valid new credentials are submitted.

## Outcome

The first Administrator account is created, setup availability is consumed, and the installer is carried to sign-in without receiving a dashboard session.
