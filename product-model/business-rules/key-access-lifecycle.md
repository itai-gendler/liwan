---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "send-event-batch",
      "contexts": [
        {
          "place": "event-ingestion::server-collection"
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
      "id": "change-api-keys-settings",
      "contexts": [
        {
          "place": "website::administration"
        }
      ]
    },
    {
      "type": "capability",
      "id": "add-entity-to-api-key",
      "contexts": [
        {
          "place": "website::administration"
        }
      ]
    },
    {
      "type": "capability",
      "id": "remove-entity-from-api-key",
      "contexts": [
        {
          "place": "website::administration"
        }
      ]
    },
    {
      "type": "capability",
      "id": "add-project-to-api-key",
      "contexts": [
        {
          "place": "website::administration"
        }
      ]
    },
    {
      "type": "capability",
      "id": "remove-project-from-api-key",
      "contexts": [
        {
          "place": "website::administration"
        }
      ]
    },
    {
      "type": "capability",
      "id": "regenerate-api-key",
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
      "target": "crates/liwan/src/web/routes/v1.rs:60"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/events.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/api_keys.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/web/routes/admin.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "packages/web/src/components/settings/api-keys.tsx"
    }
  ]
}
---

# API Key source access combines direct scope and current scoped-Project associations

Direct source scope combines with current Project membership; supported batch permission; expiry/replacement/deletion invalidate credentials; Last used at records authentication before later rejection.
