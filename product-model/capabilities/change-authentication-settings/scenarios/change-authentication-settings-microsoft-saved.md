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
      "text": "Microsoft is chosen as the provider, and its client fields and the policy are valid.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::authentication"
        }
      }
    },
    {
      "text": "The enabled provider is validated before saving, then the policy and applicable registration are saved. Existing secret material is preserved only under the implemented unchanged-client identity conditions.",
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
        },
        {
          "entity": "microsoft-registration",
          "effect": "changes",
          "facts": [
            "Client ID",
            "Client secret",
            "Secret configured",
            "Callback URL",
            "Tenant"
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

# Change Authentication settings — microsoft saved

## Trigger

Microsoft is chosen as the provider, and its client fields and the policy are valid.

## Outcome

The enabled provider is validated before saving, then the policy and applicable registration are saved. Existing secret material is preserved only under the implemented unchanged-client identity conditions.

## Edge cases

- Creating, editing and replacing the applicable provider registration follow the saved provider identity; existing raw secrets are never read back to the editor.
