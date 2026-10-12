---
{
  "kind": "primary",
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
      "text": "An existing local identity record’s username and password proof match.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "p": {
          "place": "website::public::sign-in"
        }
      }
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

# Sign in — password

## Trigger

An existing local account’s username and password proof match.

## Outcome

An expiring dashboard sign-in and browser credential pair are issued without renewal; the validated return destination is honored.

## Edge cases

- A malformed or partial browser cookie pair is rejected and cleared; successful sign-ins expire under current configured lifetime without renewal.
