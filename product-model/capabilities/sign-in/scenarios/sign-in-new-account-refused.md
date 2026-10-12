---
{
  "kind": "validation",
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
      "text": "A valid external identity has no identity record binding and new identity record creation is disabled.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "p": {
          "place": "website::public::sign-in"
        }
      }
    },
    {
      "text": "External sign-in is refused without creating an identity record or sign-in.",
      "kind": "product",
      "actor": "visitor",
      "entities": [],
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

# Sign in — new account refused

## Trigger

A valid external identity has no account binding and new account creation is disabled.

## Outcome

External sign-in is refused without creating an account or sign-in.
