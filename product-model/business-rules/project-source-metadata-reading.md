---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "entity",
      "effect": "reads",
      "facts": [
        "Entity ID",
        "Name"
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

# Visitors, Users and Administrators read source metadata through the selected accessible Project

The configuration-bearing Project is the exact accessible report or list Project containing the disclosed source. This grant permits only its associated source metadata, never independent source settings access.
