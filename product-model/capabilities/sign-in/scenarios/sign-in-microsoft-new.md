---
{
  "kind": "primary",
  "routes": {
    "p": "P — sign in"
  },
  "steps": [
    {
      "text": "The Visitor starts the configured external sign-in and completes the provider callback",
      "kind": "actor",
      "actor": "visitor",
      "entities": [],
      "contexts": {
        "p": {
          "place": "website::public::sign-in"
        }
      }
    },
    {
      "text": "Valid Microsoft external authorization completes under unchanged enabled policy; the identity has no binding and initial external-identity creation is enabled. An existing default membership group is configured for initial assignment.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "p": {
          "place": "website::public::sign-in"
        }
      }
    },
    {
      "text": "A non-administrative role Account with bound external identity and no local password is created; initial default/mapped Teams are assigned and an expiring sign-in is issued.",
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
          "entity": "team",
          "effect": "changes",
          "facts": [
            "Members"
          ]
        }
      ],
      "contexts": {
        "p": {
          "place": "website::public::sign-in"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/web/routes/external_auth.rs"
    }
  ]
}
---

# Sign in — microsoft new

## Trigger

Valid Microsoft external authorization completes under unchanged enabled policy; the identity has no binding and New user creation is enabled. An existing Default Team is configured for initial assignment.

## Outcome

A non-administrator account with bound external identity and no local password is created; initial default/mapped Teams are assigned and an expiring sign-in is issued.

## Edge cases

- With no Default Team and no exact matched provider-group mapping, signup keeps an empty Team set and changes no Team membership. Existing identities are never resynchronized.
