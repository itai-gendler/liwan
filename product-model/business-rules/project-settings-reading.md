---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "project",
      "effect": "reads",
      "facts": [
        "Project ID",
        "Name",
        "Visibility",
        "Entities",
        "Metric display",
        "Dimension display"
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

# Only Administrators read Project Project ID, Name, Visibility, Entities, Metric display, Dimension display

Administrators read the selected Project Project ID, Name, Visibility, Entities, Metric display, Dimension display in Website administration.
