---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "create-project",
      "contexts": [
        {
          "place": "website::account"
        }
      ]
    },
    {
      "type": "capability",
      "id": "create-entity",
      "contexts": [
        {
          "place": "website::account"
        }
      ]
    },
    {
      "type": "capability",
      "id": "create-user",
      "contexts": [
        {
          "place": "website::administration"
        },
        {
          "place": "liwan-cli"
        }
      ]
    },
    {
      "type": "capability",
      "id": "create-team",
      "contexts": [
        {
          "place": "website::administration"
        }
      ]
    },
    {
      "type": "capability",
      "id": "create-api-key",
      "contexts": [
        {
          "place": "website::administration"
        }
      ]
    },
    {
      "type": "capability",
      "id": "change-projects-settings",
      "contexts": [
        {
          "place": "website::administration"
        }
      ]
    },
    {
      "type": "capability",
      "id": "change-entities-settings",
      "contexts": [
        {
          "place": "website::administration"
        }
      ]
    },
    {
      "type": "capability",
      "id": "change-users-settings",
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
      "id": "change-api-keys-settings",
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
      "target": "crates/liwan/src/web/routes/admin.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/projects.rs"
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
      "target": "crates/liwan/src/cli.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/teams.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/api_keys.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "packages/web/src/components/settings/api-keys.tsx"
    }
  ]
}
---

# Settings edits preserve existing identifiers and each creation path uses its own validator

Settings edits preserve existing identifiers; validators and generated identifiers are not interchangeable. The general ID validator itself accepts empty strings, so no universal nonempty-ID guarantee is asserted.
