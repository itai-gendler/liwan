---
{
  "kind": "primary",
  "routes": {
    "r": "R — authentication"
  },
  "steps": [
    {
      "text": "The Administrator changes the selected provider-group value or destination",
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
      "text": "An existing mapping’s group value or destination membership group is edited with valid references.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::authentication"
        }
      }
    },
    {
      "text": "The mapping is saved without duplicate group values and used only for subsequent initial external identity record creation.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "team-mapping",
          "effect": "changes",
          "facts": [
            "Group value",
            "Team"
          ]
        },
        {
          "entity": "authentication-settings",
          "effect": "changes",
          "facts": [
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

# Edit Team mapping — changed

## Trigger

An existing mapping’s group value or destination Team is edited with valid references.

## Outcome

The mapping is saved without duplicate group values and used only for subsequent initial external account creation.
