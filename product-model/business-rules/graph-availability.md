---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "project",
      "effect": "reads",
      "facts": [
        "Graph"
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

# Visitors, Users and Administrators read graphs only for available requested metrics

The configuration-bearing Project is the exact selected accessible report Project. Its actual requested metric must be available under current display policy; Auto resolves current source settings and Always can expose partial history. This condition selects a graph, not summary suppression or a sample threshold.
