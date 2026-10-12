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
          "place": "website::account::projects"
        },
        {
          "place": "website::account::project-list"
        },
        {
          "place": "website::account::entity-list"
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

# Users discover Public, Internal and Team-granted Projects; Administrators discover all

Public and Internal Projects appear in signed-in discovery. Administrators discover all Projects. Private or Unlisted Projects require a current Team membership with Project-read permission and effective all or selected scope containing this exact Project. Unlisted direct access alone does not add it to discovery; associated-Project metadata is filtered by the same enumeration policy.
