---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "collection-settings",
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

# Only Administrators read Collection settings

Administrators read the selected Collection settings in Website administration.
