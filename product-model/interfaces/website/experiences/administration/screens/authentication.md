---
{
  "entities": [
    {
      "entity": "authentication-settings",
      "shows": [
        "External sign-in enabled",
        "Provider",
        "New user creation",
        "Provider session reuse",
        "Default Team",
        "Team mappings"
      ],
      "collects": [
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
      "shows": [
        "Client ID",
        "Secret configured",
        "Callback URL",
        "Issuer URL",
        "Sign-in label",
        "Additional scopes",
        "Group claim"
      ],
      "collects": [
        "Client ID",
        "Client secret",
        "Issuer URL",
        "Sign-in label",
        "Additional scopes",
        "Group claim"
      ]
    },
    {
      "entity": "google-registration",
      "shows": [
        "Client ID",
        "Secret configured",
        "Callback URL",
        "Workspace domain"
      ],
      "collects": [
        "Client ID",
        "Client secret",
        "Workspace domain"
      ]
    },
    {
      "entity": "microsoft-registration",
      "shows": [
        "Client ID",
        "Secret configured",
        "Callback URL",
        "Tenant"
      ],
      "collects": [
        "Client ID",
        "Client secret",
        "Tenant"
      ]
    },
    {
      "entity": "team-mapping",
      "shows": [
        "Group value",
        "Team"
      ],
      "collects": [
        "Group value",
        "Team"
      ]
    },
    {
      "entity": "team",
      "shows": [
        "Team ID",
        "Name"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "packages/web/src/components/settings/auth/index.tsx"
    }
  ]
}
---

# Authentication

Saved external sign-in policy, the applicable provider registration and initial-account Team assignments. Existing client secrets are represented by configured status; replacement secrets are input.
