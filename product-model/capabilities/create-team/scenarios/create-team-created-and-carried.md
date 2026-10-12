---
{
  "kind": "primary",
  "routes": {
    "r": "R — teams"
  },
  "steps": [
    {
      "text": "The Administrator supplies a new membership-group name",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::teams"
        }
      }
    },
    {
      "text": "A nonblank trimmed membership group name is submitted.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::teams"
        }
      }
    },
    {
      "text": "A generated-ID Team is created with no members or selected groupings and the supported grouping-read access configuration; the caller is carried to its membership/access editor.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "team",
          "effect": "creates",
          "facts": [
            "Team ID",
            "Name",
            "Members",
            "Project access mode",
            "Projects",
            "Permissions"
          ]
        }
      ],
      "contexts": {
        "r": {
          "place": "website::administration::teams"
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

# Create Team — created and carried

## Trigger

A nonblank trimmed Team name is submitted.

## Outcome

A generated-ID Team is created with no members or selected Projects and the supported Project-read access configuration; the caller is carried to its membership/access editor.
