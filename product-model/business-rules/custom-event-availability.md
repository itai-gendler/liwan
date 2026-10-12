---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "project",
      "effect": "reads",
      "facts": [
        "Views",
        "Unique visitors",
        "Bounce rate",
        "Time on site",
        "Comparison",
        "Graph",
        "Dimension breakdowns",
        "Bounce-rate breakdowns",
        "Time-on-site breakdowns",
        "Property breakdowns",
        "Custom-event breakdowns"
      ],
      "contexts": [
        {
          "place": "website::public"
        },
        {
          "place": "website::account"
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
      "configuredBy": "project"
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

# Visitors, Users and Administrators read named-event results only when custom-event display is visible

This conjunctive configuration grant binds the exact selected Project and the actual report request. An explicitly selected event name other than pageview, or a custom-event breakdown request, requires that Project’s Custom-event display not be Hidden. A pageview selection does not require custom-event display, and this Rule does not suppress its Views, uniques, session summary, graph or dimensions. Ordinary Project access and the requested metric/dimension Rules also apply. Unsupported named-event session metrics and filters are separately rejected as input validation.
