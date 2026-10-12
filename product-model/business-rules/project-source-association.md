---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "project",
      "effect": "changes",
      "facts": [
        "Entities"
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

# Only Administrators change Project Entities

Administrators change the selected Project Entities in Website administration.
