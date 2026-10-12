---
{
  "kind": "primary",
  "routes": {
    "r": "R — team settings"
  },
  "steps": [
    {
      "text": "The Administrator opens the selected membership/access editor",
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
      "text": "The selected membership group exists.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::team-settings"
        }
      }
    },
    {
      "text": "Its name, members and grouping access mode/scope are shown. Website saves maintain the supported grouping-read permission rather than editing an independent permission list.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "team",
          "effect": "reads",
          "facts": [
            "Team ID",
            "Name",
            "Members",
            "Project access mode",
            "Projects"
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

# View Team settings — selected team

## Trigger

The selected Team exists.

## Outcome

Its name, members and Project access mode/scope are shown. Website saves maintain the supported Project-read permission rather than editing an independent permission list.
