---
{
  "kind": "primary",
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
      "text": "Internal-only operation is selected.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::authentication"
        }
      }
    },
    {
      "text": "External sign-in is disabled without promising deletion of retained registration or external identity bindings.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "authentication-settings",
          "effect": "changes",
          "facts": [
            "External sign-in enabled",
            "Provider",
            "New user creation",
            "Provider session reuse",
            "Default Team",
            "Team mappings"
          ]
        }
      ],
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

# Change Authentication settings — internal only saved

## Trigger

Internal-only operation is selected.

## Outcome

External sign-in is disabled without promising deletion of retained registration or external identity bindings.

## Edge cases

- Creating, editing and replacing the applicable provider registration follow the saved provider identity; existing raw secrets are never read back to the editor.
