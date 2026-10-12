---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "team-mapping",
      "effect": "reads",
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

# Only Administrators read Team mapping

Administrators read the selected Team mapping in Website administration.
