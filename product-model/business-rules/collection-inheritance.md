---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "change-collection-settings",
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
      "id": "add-drop-rule",
      "contexts": [
        {
          "place": "website::administration"
        }
      ]
    },
    {
      "type": "capability",
      "id": "edit-drop-rule",
      "contexts": [
        {
          "place": "website::administration"
        }
      ]
    },
    {
      "type": "capability",
      "id": "remove-drop-rule",
      "contexts": [
        {
          "place": "website::administration"
        }
      ]
    },
    {
      "type": "capability",
      "id": "send-event",
      "contexts": [
        {
          "place": "event-ingestion::public-collection"
        }
      ]
    },
    {
      "type": "capability",
      "id": "record-page-exit",
      "contexts": [
        {
          "place": "event-ingestion::public-collection"
        }
      ]
    },
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
      "id": "prune-events",
      "contexts": [
        {
          "place": "website::administration"
        },
        {
          "place": "liwan-cli"
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
      "target": "crates/liwan/src/app/core/settings.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/entities.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/web/routes/event.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/events.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "packages/tracker/src/script.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/web/routes/v1.rs:60"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/api_keys.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/cli.rs"
    }
  ]
}
---

# Entity overrides inherit global defaults and Drop rules accumulate

Source overrides resolve against global defaults; global/source rules accumulate; policy changes affect subsequent processing and explicit pruning. Defaults are Accurate grouping, session/campaign collection enabled, city detail and keep all. Source inheritance is per setting; empty allowed hostnames admit all. Later policy changes do not automatically rewrite stored history.
