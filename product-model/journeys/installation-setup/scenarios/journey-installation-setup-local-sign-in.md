---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Website"
  },
  "steps": [
    {
      "text": "The Visitor supplies the setup token, username and new password",
      "kind": "actor",
      "actor": "visitor",
      "entities": [],
      "contexts": {
        "web": {
          "place": "website::public::setup"
        }
      },
      "capability": "finish-setup"
    },
    {
      "text": "No identity record existed at startup and initial setup remains available. A valid token and valid new credentials are submitted.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "web": {
          "place": "website::public::setup"
        }
      },
      "capability": "finish-setup"
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
        "web": {
          "place": "website::public::setup"
        }
      },
      "capability": "finish-setup"
    },
    {
      "text": "The Product carries the caller to the sign-in process",
      "kind": "product",
      "actor": "visitor",
      "entities": [],
      "capability": "finish-setup",
      "contexts": {
        "web": {
          "place": "website::public::setup"
        }
      }
    },
    {
      "text": "The Visitor submits a username and local password proof",
      "kind": "actor",
      "actor": "visitor",
      "entities": [],
      "contexts": {
        "web": {
          "place": "website::public::sign-in"
        }
      },
      "capability": "sign-in"
    },
    {
      "text": "An existing local identity record’s username and password proof match.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "web": {
          "place": "website::public::sign-in"
        }
      },
      "capability": "sign-in"
    },
    {
      "text": "An expiring dashboard sign-in and browser credential pair are issued without renewal; the validated return destination is honored.",
      "kind": "product",
      "actor": "visitor",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Sign-ins"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "website::public::sign-in"
        }
      },
      "capability": "sign-in"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/web/routes/external_auth.rs"
    }
  ]
}
---

# Installation setup — local sign in

## Trigger

Create the initial administrator and establish the first local dashboard sign-in.

## Outcome

Initial creation succeeds, setup is consumed, and the installer subsequently signs in.
