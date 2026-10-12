---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "delete-entity",
      "contexts": [
        {
          "place": "website::administration"
        }
      ]
    },
    {
      "type": "capability",
      "id": "delete-project",
      "contexts": [
        {
          "place": "website::administration"
        }
      ]
    },
    {
      "type": "capability",
      "id": "delete-user",
      "contexts": [
        {
          "place": "website::administration"
        }
      ]
    },
    {
      "type": "capability",
      "id": "delete-team",
      "contexts": [
        {
          "place": "website::administration"
        }
      ]
    },
    {
      "type": "capability",
      "id": "delete-api-key",
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
      "target": "crates/liwan/src/app/core/entities.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/projects.rs"
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

# Entity and Project deletion retain stored event history

Inspected dependent cleanup; Entity/Project deletion preserves event history; reused source IDs may reconnect retained history.
