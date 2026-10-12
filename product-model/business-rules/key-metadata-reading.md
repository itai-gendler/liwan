---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "api-key",
      "effect": "reads",
      "facts": [
        "Key ID",
        "Name",
        "Permissions",
        "Entity access mode",
        "Entities",
        "Project access mode",
        "Projects",
        "Created at",
        "Expires at",
        "Last used at"
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

# Only Administrators read API Key Key ID, Name, Permissions, Entity access mode, Entities, Project access mode, Projects, Created at, Expires at, Last used at

Administrators read the selected API Key Key ID, Name, Permissions, Entity access mode, Entities, Project access mode, Projects, Created at, Expires at, Last used at in Website administration.
