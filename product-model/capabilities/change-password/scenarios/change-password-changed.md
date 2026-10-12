---
{
  "kind": "primary",
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
      "text": "Current password proof matches the retained local credential and the new password meets the Website constraints.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "a": {
          "place": "website::account::my-account"
        }
      }
    },
    {
      "text": "The local credential is replaced using guarded comparison, other sign-ins are revoked, and the current sign-in is retained.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Local credential",
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
      "target": "packages/web/src/components/settings/me/index.tsx"
    }
  ]
}
---

# Change password — changed

## Trigger

Current password proof matches the retained local credential and the new password meets the Website constraints.

## Outcome

The local credential is replaced using guarded comparison, other sign-ins are revoked, and the current sign-in is retained.
