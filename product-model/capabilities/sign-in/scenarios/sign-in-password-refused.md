---
{
  "kind": "validation",
  "routes": {
    "p": "P — sign in"
  },
  "steps": [
    {
      "text": "The Visitor submits a username and local password proof",
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
      "text": "Local username/password proof does not match, or local proof processing fails.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "p": {
          "place": "website::public::sign-in"
        }
      }
    },
    {
      "text": "The attempt returns invalid username/password and creates no sign-in.",
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

# Sign in — password refused

## Trigger

Local username/password proof does not match, or local proof processing fails.

## Outcome

The attempt returns invalid username/password and creates no sign-in.
