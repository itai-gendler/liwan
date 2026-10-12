---
{
  "kind": "primary",
  "routes": {
    "r": "R — authentication"
  },
  "steps": [
    {
      "text": "The Administrator removes the selected provider-group mapping",
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
      "text": "An existing group mapping is selected for removal.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::authentication"
        }
      }
    },
    {
      "text": "The mapping is removed from external configuration; existing identity record memberships are not continuously resynchronized.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "team-mapping",
          "effect": "removes"
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

# Remove Team mapping — removed

## Trigger

An existing group mapping is selected for removal.

## Outcome

The mapping is removed from external configuration; existing account memberships are not continuously resynchronized.
