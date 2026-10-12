---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "drop-rule",
      "effect": "changes",
      "facts": [
        "Conditions"
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

# Only Administrators change Drop rule Conditions

Administrators change the selected Drop rule Conditions in Website administration.
