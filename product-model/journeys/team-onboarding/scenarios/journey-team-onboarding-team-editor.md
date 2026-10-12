---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Website"
  },
  "steps": [
    {
      "text": "The Administrator supplies a new membership-group name",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "web": {
          "place": "website::administration::teams"
        }
      },
      "capability": "create-team"
    },
    {
      "text": "A nonblank trimmed membership group name is submitted.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "web": {
          "place": "website::administration::teams"
        }
      },
      "capability": "create-team"
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
        "web": {
          "place": "website::administration::teams"
        }
      },
      "capability": "create-team"
    },
    {
      "text": "The Product carries the caller to the new membership and access editor",
      "kind": "product",
      "actor": "administrator",
      "entities": [],
      "capability": "create-team",
      "contexts": {
        "web": {
          "place": "website::administration::teams"
        }
      }
    },
    {
      "text": "The Administrator opens the selected membership/access editor",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "web": {
          "place": "website::administration::team-settings"
        }
      },
      "capability": "view-team-settings"
    },
    {
      "text": "The selected membership group exists.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "web": {
          "place": "website::administration::team-settings"
        }
      },
      "capability": "view-team-settings"
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
        "web": {
          "place": "website::administration::team-settings"
        }
      },
      "capability": "view-team-settings"
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

# Team onboarding — team editor

## Trigger

Create a Team and reach its membership and access editor.

## Outcome

The generated Team exists and its current membership/access settings have been read.
