---
{
  "kind": "edge",
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
      "text": "Enabled provider validation cannot reach usable discovery or registration validation.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::authentication"
        }
      }
    },
    {
      "text": "Saving fails before persisting the proposed enabled configuration; the preceding saved policy remains.",
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

# Change Authentication settings — provider validation unavailable

## Trigger

Enabled provider validation cannot reach usable discovery or registration validation.

## Outcome

Saving fails before persisting the proposed enabled configuration; the preceding saved policy remains.
