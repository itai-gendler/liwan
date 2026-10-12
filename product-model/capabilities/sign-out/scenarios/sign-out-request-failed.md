---
{
  "kind": "edge",
  "routes": {
    "a": "A — my account",
    "r": "R — project settings"
  },
  "steps": [
    {
      "text": "The Administrator requests browser sign-out",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "a": {
          "place": "website::account::my-account"
        },
        "r": {
          "place": "website::administration::project-settings"
        }
      }
    },
    {
      "text": "The client sign-out request cannot complete.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "a": {
          "place": "website::account::my-account"
        },
        "r": {
          "place": "website::administration::project-settings"
        }
      }
    },
    {
      "text": "The client exposes failure and does not promise carrying navigation or completed credential removal. A server database-expiry error alone still clears browser cookies.",
      "kind": "product",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "a": {
          "place": "website::account::my-account"
        },
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

# Sign out — request failed

## Trigger

The client sign-out request cannot complete.

## Outcome

The client exposes failure and does not promise carrying navigation or completed credential removal. A server database-expiry error alone still clears browser cookies.
