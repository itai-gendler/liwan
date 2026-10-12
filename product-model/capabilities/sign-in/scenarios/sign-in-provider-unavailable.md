---
{
  "kind": "edge",
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
      "text": "External discovery, authorization/token exchange or required provider verification cannot complete, or the sign-in throttle is reached.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "p": {
          "place": "website::public::sign-in"
        }
      }
    },
    {
      "text": "An observable failed/throttled sign-in is returned; no successful session is reported.",
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

# Sign in — provider unavailable

## Trigger

External discovery, authorization/token exchange or required provider verification cannot complete, or the sign-in throttle is reached.

## Outcome

An observable failed/throttled sign-in is returned; no successful session is reported.
