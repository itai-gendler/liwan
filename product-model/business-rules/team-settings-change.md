---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "team",
      "effect": "changes",
      "facts": [
        "Name",
        "Project access mode",
        "Projects",
        "Permissions"
      ],
      "contexts": [
        {
          "place": "website::administration"
        }
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "administrator"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/web/routes/admin.rs"
    }
  ]
}
---

# Only Administrators change Team Name, Project access mode, Projects, Permissions

Administrators change the selected Team Name, Project access mode, Projects, Permissions in Website administration.
