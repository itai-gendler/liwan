---
{
  "kind": "primary",
  "routes": {
    "r": "R — project settings"
  },
  "steps": [
    {
      "text": "The Administrator requests browser sign-out",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::project-settings"
        }
      }
    },
    {
      "text": "A browser sign-in exists at the selected origin.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::project-settings"
        }
      }
    },
    {
      "text": "The browser credential pair is cleared and the person is carried to public grouping discovery. Current database session expiry is attempted; an expiry error is logged and does not prevent cookie clearance.",
      "kind": "product",
      "actor": "administrator",
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
        "r": {
          "place": "website::administration::project-settings"
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

# Sign out — administration ended

## Trigger

A browser sign-in exists at the selected origin.

## Outcome

The browser credential pair is cleared and the person is carried to public Project discovery. Current database session expiry is attempted; an expiry error is logged and does not prevent cookie clearance.
