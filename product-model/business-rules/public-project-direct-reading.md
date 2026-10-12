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
      ],
      "contexts": [
        {
          "place": "website::public"
        }
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "visitor",
        "user",
        "administrator"
      ],
      "when": [
        {
          "fact": "Visibility",
          "is": "Public"
        }
      ]
    },
    {
      "actors": [
        "visitor",
        "user",
        "administrator"
      ],
      "when": [
        {
          "fact": "Visibility",
          "is": "Unlisted"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/utils/validate.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/web/routes/dashboard.rs"
    }
  ]
}
---

# Visitors and unsigned roleholders read Public or Unlisted Project reports

Public or Unlisted visibility permits direct report reading without a session. Internal and Private Projects do not qualify through this public grant.
