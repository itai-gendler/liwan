---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "entity",
      "effect": "reads",
      "facts": [
        "Entity ID",
        "Name",
        "Projects",
        "Allowed hostnames"
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

# Only Administrators read Entity Entity ID, Name, Projects, Allowed hostnames

Administrators read the selected Entity Entity ID, Name, Projects, Allowed hostnames in Website administration.
