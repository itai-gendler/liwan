---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "project",
      "effect": "reads",
      "facts": [
        "Dimension breakdowns",
        "Bounce-rate breakdowns",
        "Time-on-site breakdowns",
        "Property breakdowns"
      ],
      "contexts": [
        {
          "place": "website::public::project"
        },
        {
          "place": "website::account::project"
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

# Visitors, Users and Administrators read breakdowns only for available requested metrics and dimensions

The configuration-bearing Project is the exact selected accessible report Project. Its actual requested metric and dimension must both be available under current display policy. Auto resolves current source settings; Always may expose partial history. A hidden dimension can still be used as a filter, and sample minima are derivations rather than permission conditions.
