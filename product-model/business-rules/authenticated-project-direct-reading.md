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
          "place": "website::account"
        }
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "user"
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
        "user"
      ],
      "when": [
        {
          "fact": "Visibility",
          "is": "Unlisted"
        }
      ]
    },
    {
      "actors": [
        "user"
      ],
      "when": [
        {
          "fact": "Visibility",
          "is": "Internal"
        }
      ]
    },
    {
      "actors": [
        "administrator"
      ]
    },
    {
      "actors": [
        "user"
      ],
      "configuredBy": "team"
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

# Users read Public, Unlisted and Internal Projects or Projects granted by their Teams; Administrators read all

Users directly read Public, Unlisted or Internal Projects. An Administrator reads any Project. For other access, the configured Team must be a current membership of the acting Account, have Project-read permission, and include this exact Project in all or selected scope. Grants combine across eligible memberships; an unrelated Team never qualifies.
