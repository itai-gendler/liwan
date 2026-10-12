---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "project",
      "effect": "creates",
      "contexts": [
        {
          "place": "website::account::project-list"
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

# Only Administrators create Project

Administrators create the selected Project in project list.
