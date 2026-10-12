---
{
  "kind": "primary",
  "routes": {
    "a": "A — my account"
  },
  "steps": [
    {
      "text": "The User requests browser sign-out",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "a": {
          "place": "website::account::my-account"
        }
      }
    },
    {
      "text": "A browser sign-in exists at the selected origin.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "a": {
          "place": "website::account::my-account"
        }
      }
    },
    {
      "text": "The browser credential pair is cleared and the person is carried to public grouping discovery. Current database session expiry is attempted; an expiry error is logged and does not prevent cookie clearance.",
      "kind": "product",
      "actor": "user",
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
        "a": {
          "place": "website::account::my-account"
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

# Sign out — account ended

## Trigger

A browser sign-in exists at the selected origin.

## Outcome

The browser credential pair is cleared and the person is carried to public Project discovery. Current database session expiry is attempted; an expiry error is logged and does not prevent cookie clearance.
