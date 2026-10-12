---
{
  "kind": "validation",
  "routes": {
    "a": "A — my account"
  },
  "steps": [
    {
      "text": "The User supplies current-password proof, a new password and confirmation",
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
      "text": "The new password is too short or the browser confirmation differs.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "a": {
          "place": "website::account::my-account"
        }
      }
    },
    {
      "text": "The edit is refused before successful password replacement.",
      "kind": "product",
      "actor": "user",
      "entities": [],
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
      "target": "packages/web/src/components/settings/me/index.tsx"
    }
  ]
}
---

# Change password — new password refused

## Trigger

The new password is too short or the browser confirmation differs.

## Outcome

The edit is refused before successful password replacement.
