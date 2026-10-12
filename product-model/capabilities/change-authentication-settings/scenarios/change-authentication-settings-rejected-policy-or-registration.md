---
{
  "kind": "validation",
  "routes": {
    "r": "R — authentication"
  },
  "steps": [
    {
      "text": "The Administrator selects a provider or internal-only policy and submits applicable client fields",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::authentication"
        }
      }
    },
    {
      "text": "The proposed policy, registration, scopes/claim, mapping references, duplicate values or supported mapping limit is invalid.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::authentication"
        }
      }
    },
    {
      "text": "Validation refuses the proposed configuration before successful persistence. Google group mappings are unsupported.",
      "kind": "product",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::authentication"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/web/routes/external_auth.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/external_auth/mod.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "packages/web/src/components/settings/auth/index.tsx"
    }
  ]
}
---

# Change Authentication settings — rejected policy or registration

## Trigger

The proposed policy, registration, scopes/claim, mapping references, duplicate values or supported mapping limit is invalid.

## Outcome

Validation refuses the proposed configuration before successful persistence. Google group mappings are unsupported.
