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
      "text": "External sign-in is enabled with a saved Provider.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::authentication"
        }
      }
    },
    {
      "text": "The saved policy and the saved Provider's registration, secret-configured status, callback address and initial-membership group mappings are shown; existing raw client secrets are not disclosed.",
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
          "entity": "openid-connect-registration",
          "effect": "reads",
          "facts": [
            "Client ID",
            "Secret configured",
            "Callback URL",
            "Issuer URL",
            "Sign-in label",
            "Additional scopes",
            "Group claim"
          ]
        },
        {
          "entity": "google-registration",
          "effect": "reads",
          "facts": [
            "Client ID",
            "Secret configured",
            "Callback URL",
            "Workspace domain"
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

# View Authentication settings — configured provider

## Trigger

External sign-in is enabled with a saved Provider.

## Outcome

The saved policy and the saved Provider's registration, secret-configured status, callback address and initial-Team mappings are shown; existing raw client secrets are not disclosed.

## Decision points

### Registration shown

Which registration fields are shown?

- The saved Provider is OpenID Connect → its Issuer URL, Sign-in label, Additional scopes, Group claim and Team mappings are shown with the client fields.
- The saved Provider is Google → its optional Workspace domain is shown with the client fields; Google has no Team mappings.
- The saved Provider is Microsoft → its Tenant and Team mappings are shown with the client fields.
