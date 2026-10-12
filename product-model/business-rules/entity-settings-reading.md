---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "entity",
      "effect": "reads",
      "facts": [
        "Visitor grouping",
        "Session collection",
        "Campaign collection",
        "Location detail",
        "History retention",
        "Drop rules",
        "Effective collection settings",
        "Custom-data presence",
        "Tracking snippet"
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

# Only Administrators read Entity Visitor grouping, Session collection, Campaign collection, Location detail, History retention, Drop rules, Effective collection settings, Custom-data presence, Tracking snippet

Administrators read the selected Entity Visitor grouping, Session collection, Campaign collection, Location detail, History retention, Drop rules, Effective collection settings, Custom-data presence, Tracking snippet in Website administration.
