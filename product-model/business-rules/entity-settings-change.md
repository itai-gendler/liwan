---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "entity",
      "effect": "changes",
      "facts": [
        "Name",
        "Visitor grouping",
        "Session collection",
        "Campaign collection",
        "Location detail",
        "History retention",
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

# Only Administrators change Entity Name, Visitor grouping, Session collection, Campaign collection, Location detail, History retention, Allowed hostnames

Administrators change the selected Entity Name, Visitor grouping, Session collection, Campaign collection, Location detail, History retention, Allowed hostnames in Website administration.
