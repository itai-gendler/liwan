---
{
  "entities": [
    {
      "entity": "team",
      "shows": [
        "Team ID",
        "Name",
        "Members",
        "Project access mode",
        "Projects"
      ],
      "collects": [
        "Name",
        "Members",
        "Project access mode",
        "Projects"
      ]
    },
    {
      "entity": "account",
      "shows": [
        "Username",
        "Administrator access"
      ]
    },
    {
      "entity": "project",
      "shows": [
        "Project ID",
        "Name",
        "Visibility",
        "Entities"
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

# Team settings

One Team’s name, members and Project scope. The Website fixes Project-read permission while saving scope rather than providing an independent permission editor.
