---
{
  "entities": [
    {
      "entity": "project",
      "shows": [
        "Project ID",
        "Name",
        "Visibility",
        "Entities",
        "Report availability",
        "Views",
        "Unique visitors",
        "Bounce rate",
        "Time on site",
        "Current visitors",
        "Comparison",
        "Graph"
      ]
    },
    {
      "entity": "dashboard-preferences",
      "shows": [
        "Selected metric",
        "Selected range"
      ],
      "collects": [
        "Selected metric",
        "Selected range"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/web/routes/dashboard.rs"
    }
  ]
}
---

# Projects

Project discovery with overview reports and browser metric/range preferences.
