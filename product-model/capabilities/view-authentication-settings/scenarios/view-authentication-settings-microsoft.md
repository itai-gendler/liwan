---
{
  "kind": "primary",
  "routes": {
    "r": "R — authentication"
  },
  "steps": [
    {
      "text": "The Administrator opens external sign-in configuration",
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
      "text": "The saved enabled provider is Microsoft.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::authentication"
        }
      }
    },
    {
      "text": "The saved policy and applicable provider registration, secret-configured status, callback address and initial-membership group mappings are shown; existing raw client secrets are not disclosed.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "authentication-settings",
          "effect": "reads",
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
          "effect": "reads",
          "facts": [
            "Client ID",
            "Secret configured",
            "Callback URL",
            "Tenant"
          ]
        },
        {
          "entity": "team-mapping",
          "effect": "reads",
          "facts": [
            "Group value",
            "Team"
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

# View Authentication settings — microsoft

## Trigger

The saved enabled provider is Microsoft.

## Outcome

The saved policy and applicable provider registration, secret-configured status, callback address and initial-Team mappings are shown; existing raw client secrets are not disclosed.
