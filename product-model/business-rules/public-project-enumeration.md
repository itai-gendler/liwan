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
        "Entities"
      ],
      "contexts": [
        {
          "place": "website::public::projects"
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

# Visitors and unsigned roleholders discover only Public Projects

Only Public visibility qualifies for unsigned discovery. Unlisted direct access does not put a Project in this list.
