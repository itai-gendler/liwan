---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "drop-rule",
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

# Only Administrators read Drop rule

Administrators read the selected Drop rule in Website administration.
