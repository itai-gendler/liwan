---
{
  "entities": [
    {
      "entity": "team",
      "shows": [
        "Team ID",
        "Name",
        "Members"
      ],
      "collects": [
        "Name"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "packages/web/src/components/settings/teams/index.tsx"
    }
  ]
}
---

# Teams

Team discovery shows names and member counts, with a name input for creating a new Team.
