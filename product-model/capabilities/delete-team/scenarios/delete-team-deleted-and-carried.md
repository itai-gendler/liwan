---
{
  "kind": "primary",
  "routes": {
    "r": "R — team settings"
  },
  "steps": [
    {
      "text": "The Administrator confirms deletion of the selected membership group",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::team-settings"
        }
      }
    },
    {
      "text": "Deletion of the selected membership group is confirmed.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::team-settings"
        }
      }
    },
    {
      "text": "The Team and memberships/access grants are removed, applicable default-Team references and provider mappings are cleaned up, and the caller is carried to the remaining-Team list.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "team",
          "effect": "removes"
        },
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Teams"
          ]
        },
        {
          "entity": "authentication-settings",
          "effect": "changes",
          "facts": [
            "Default Team",
            "Team mappings"
          ]
        },
        {
          "entity": "team-mapping",
          "effect": "removes",
          "with": "team"
        }
      ],
      "contexts": {
        "r": {
          "place": "website::administration::team-settings"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/web/routes/admin.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/teams.rs"
    }
  ]
}
---

# Delete Team — deleted and carried

## Trigger

Deletion of the selected Team is confirmed.

## Outcome

The Team and memberships/access grants are removed, applicable default-Team references and provider mappings are cleaned up, and the caller is carried to the remaining-Team list.
