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
        "Graph",
        "Dimension breakdowns",
        "Bounce-rate breakdowns",
        "Time-on-site breakdowns",
        "Custom-event breakdowns",
        "Property breakdowns",
        "Earliest event"
      ]
    },
    {
      "entity": "entity",
      "shows": [
        "Entity ID",
        "Name"
      ]
    },
    {
      "entity": "dashboard-preferences",
      "shows": [
        "Selected metric",
        "Selected range",
        "Selected interval"
      ],
      "collects": [
        "Selected metric",
        "Selected range",
        "Selected interval"
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

# Project

The selected Project report, including transient filters and event selection.
