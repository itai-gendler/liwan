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
      "text": "The old proof does not match, including an identity record lacking a local credential.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "a": {
          "place": "website::account::my-account"
        }
      }
    },
    {
      "text": "The current-password error is returned and no credential overwrite or session revocation occurs.",
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

# Change password — current password refused

## Trigger

The old proof does not match, including an account lacking a local credential.

## Outcome

The current-password error is returned and no credential overwrite or session revocation occurs.
