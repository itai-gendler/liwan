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
      "text": "External sign-in is disabled.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::authentication"
        }
      }
    },
    {
      "text": "The saved disabled policy is presented. Its registration is retained and can be restored by selecting that provider; existing raw secrets are not exposed.",
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

# View Authentication settings — internal only

## Trigger

External sign-in is disabled.

## Outcome

The saved disabled policy is presented. Its registration is retained and can be restored by selecting that provider; existing raw secrets are not exposed.
