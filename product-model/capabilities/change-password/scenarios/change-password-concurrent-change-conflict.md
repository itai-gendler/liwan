---
{
  "kind": "edge",
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
      "text": "Verification matched an older credential but another replacement wins before guarded persistence.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "a": {
          "place": "website::account::my-account"
        }
      }
    },
    {
      "text": "The stale replacement is refused, preserving the winning credential rather than overwriting it.",
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

# Change password — concurrent change conflict

## Trigger

Verification matched an older credential but another replacement wins before guarded persistence.

## Outcome

The stale replacement is refused, preserving the winning credential rather than overwriting it.
