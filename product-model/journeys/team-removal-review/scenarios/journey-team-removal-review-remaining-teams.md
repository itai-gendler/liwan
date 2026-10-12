---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Website"
  },
  "steps": [
    {
      "text": "The Administrator confirms deletion of the selected membership group",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "web": {
          "place": "website::administration::team-settings"
        }
      },
      "capability": "delete-team"
    },
    {
      "text": "Deletion of the selected membership group is confirmed.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "web": {
          "place": "website::administration::team-settings"
        }
      },
      "capability": "delete-team"
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
        "web": {
          "place": "website::administration::team-settings"
        }
      },
      "capability": "delete-team"
    },
    {
      "text": "The Product carries the caller to the remaining-membership-group list",
      "kind": "product",
      "actor": "administrator",
      "entities": [],
      "capability": "delete-team",
      "contexts": {
        "web": {
          "place": "website::administration::team-settings"
        }
      }
    },
    {
      "text": "The Administrator requests the membership-group list",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "web": {
          "place": "website::administration::teams"
        }
      },
      "capability": "browse-teams"
    },
    {
      "text": "The membership group list is requested.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "web": {
          "place": "website::administration::teams"
        }
      },
      "capability": "browse-teams"
    },
    {
      "text": "Team identities, names and member counts are returned.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "team",
          "effect": "reads",
          "facts": [
            "Team ID",
            "Name",
            "Members"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "website::administration::teams"
        }
      },
      "capability": "browse-teams"
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

# Team removal review — remaining teams

## Trigger

Remove a Team and inspect remaining Teams.

## Outcome

The Team and dependent grants are removed and the remaining-Team list is read.
