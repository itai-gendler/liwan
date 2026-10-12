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
      "text": "Valid OIDC external authorization completes under unchanged enabled policy; the identity already has an identity record binding.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "p": {
          "place": "website::public::sign-in"
        }
      }
    },
    {
      "text": "The existing bound Account receives an expiring sign-in without email/username merging or continuous membership group resynchronization.",
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

# Sign in — oidc existing

## Trigger

Valid OIDC external authorization completes under unchanged enabled policy; the identity already has an account binding.

## Outcome

The existing bound account receives an expiring sign-in without email/username merging or continuous Team resynchronization.
