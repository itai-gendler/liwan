---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "drop-rule",
      "effect": "removes",
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

# Only Administrators remove Drop rule

Administrators remove the selected Drop rule in Website administration.
