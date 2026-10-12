---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "drop-rule",
      "effect": "creates",
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

# Only Administrators create Drop rule

Administrators create the selected Drop rule in Website administration.
