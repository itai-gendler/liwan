---
{
  "kind": "primary",
  "routes": {
    "r": "R — authentication"
  },
  "steps": [
    {
      "text": "The Administrator supplies an unused provider-group value and existing membership-group target",
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
      "text": "A supported mapping provider, unused nonempty exact group value and existing destination membership group are selected.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::authentication"
        }
      }
    },
    {
      "text": "One group-to-provider-group entry is added within the configured limit, used only for newly created external identity records.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "team-mapping",
          "effect": "creates",
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

# Add Team mapping — added

## Trigger

A supported mapping provider, unused nonempty exact group value and existing destination Team are selected.

## Outcome

One group-to-Team mapping is added within the configured limit, used only for newly created external accounts.
