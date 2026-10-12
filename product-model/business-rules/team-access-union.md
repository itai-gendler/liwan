---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "browse-projects",
      "contexts": [
        {
          "place": "website::public"
        },
        {
          "place": "website::account"
        }
      ]
    },
    {
      "type": "capability",
      "id": "browse-project-analytics",
      "contexts": [
        {
          "place": "website::public"
        },
        {
          "place": "website::account"
        }
      ]
    },
    {
      "type": "capability",
      "id": "browse-entities",
      "contexts": [
        {
          "place": "website::account"
        }
      ]
    },
    {
      "type": "capability",
      "id": "add-user-to-team",
      "contexts": [
        {
          "place": "website::administration"
        }
      ]
    },
    {
      "type": "capability",
      "id": "remove-user-from-team",
      "contexts": [
        {
          "place": "website::administration"
        }
      ]
    },
    {
      "type": "capability",
      "id": "change-teams-settings",
      "contexts": [
        {
          "place": "website::administration"
        }
      ]
    },
    {
      "type": "capability",
      "id": "add-project-to-team",
      "contexts": [
        {
          "place": "website::administration"
        }
      ]
    },
    {
      "type": "capability",
      "id": "remove-project-from-team",
      "contexts": [
        {
          "place": "website::administration"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/web/routes/dashboard.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/projects.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/web/routes/admin.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/entities.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/users.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/teams.rs"
    }
  ]
}
---

# Eligible current Team Project grants combine and all scope dominates selected scope

Current eligible Team Project grants combine; all scope dominates selected scope. Declared Entity-read vocabulary does not independently authorize source enumeration.
