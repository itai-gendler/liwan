---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "project",
      "effect": "changes",
      "facts": [
        "Name",
        "Visibility",
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

# Only Administrators change Project Name, Visibility, Metric display, Dimension display

Administrators change the selected Project Name, Visibility, Metric display, Dimension display in Website administration.
