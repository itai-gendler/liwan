---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "change-authentication-settings",
      "contexts": [
        {
          "place": "website::administration"
        }
      ]
    },
    {
      "type": "capability",
      "id": "add-team-mapping",
      "contexts": [
        {
          "place": "website::administration"
        }
      ]
    },
    {
      "type": "capability",
      "id": "edit-team-mapping",
      "contexts": [
        {
          "place": "website::administration"
        }
      ]
    },
    {
      "type": "capability",
      "id": "remove-team-mapping",
      "contexts": [
        {
          "place": "website::administration"
        }
      ]
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

# Enabled provider registration is validated before saving and secret retention requires matching client identity

Validate enabled configuration before persistence; preserve secret only under the implemented client-identity conditions; enforce scopes/claims/mapping limits and Google’s unsupported mapping behavior. Mapping group values are exact and unique; the configured list is bounded to 100 existing-Team mappings. OpenID Connect scopes/group claims and Microsoft tenant/Google Workspace restrictions follow their own registration shapes. A Provider other than OpenID Connect, Google or Microsoft is rejected.
