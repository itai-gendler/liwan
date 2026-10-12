---
{
  "kind": "primary",
  "routes": {
    "r": "R — team settings"
  },
  "steps": [
    {
      "text": "The Administrator submits the name or no/selected/all access mode",
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
      "text": "A valid existing membership group name or no/selected/all grouping scope mode is submitted.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::team-settings"
        }
      }
    },
    {
      "text": "The name or access mode is saved. The Website fixes grouping-read permission, and validated selected references and members are saved together by the backend.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "team",
          "effect": "changes",
          "facts": [
            "Name",
            "Project access mode",
            "Permissions"
          ]
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

# Change Teams settings — name or access mode saved

## Trigger

A valid existing Team name or no/selected/all Project scope mode is submitted.

## Outcome

The name or access mode is saved. The Website fixes Project-read permission, and validated selected references and members are saved together by the backend.
