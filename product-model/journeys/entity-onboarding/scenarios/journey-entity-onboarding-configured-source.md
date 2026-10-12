---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Website"
  },
  "steps": [
    {
      "text": "The Administrator supplies a new source ID and name",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "web": {
          "place": "website::account::entity-list"
        }
      },
      "capability": "create-entity"
    },
    {
      "text": "A new valid source ID and name are submitted.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "web": {
          "place": "website::account::entity-list"
        }
      },
      "capability": "create-entity"
    },
    {
      "text": "The source is created with empty grouping associations, inheriting collection defaults and an empty allowed-host list, and the caller is carried to its settings/snippet editor.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "entity",
          "effect": "creates",
          "facts": [
            "Entity ID",
            "Name",
            "Projects",
            "Visitor grouping",
            "Session collection",
            "Campaign collection",
            "Location detail",
            "History retention",
            "Allowed hostnames",
            "Drop rules"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "website::account::entity-list"
        }
      },
      "capability": "create-entity"
    },
    {
      "text": "The Product carries the caller to the new source settings and installation snippet",
      "kind": "product",
      "actor": "administrator",
      "entities": [],
      "capability": "create-entity",
      "contexts": {
        "web": {
          "place": "website::account::entity-list"
        }
      }
    },
    {
      "text": "The Administrator opens the selected source settings and snippet",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "web": {
          "place": "website::administration::entity-settings"
        }
      },
      "capability": "view-entity-settings"
    },
    {
      "text": "The selected source exists.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "web": {
          "place": "website::administration::entity-settings"
        }
      },
      "capability": "view-entity-settings"
    },
    {
      "text": "Source identity, associations, collection overrides, resolved policy, allowed hostnames, filter entries and installation snippet are shown.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "entity",
          "effect": "reads",
          "facts": [
            "Entity ID",
            "Name",
            "Projects",
            "Visitor grouping",
            "Session collection",
            "Campaign collection",
            "Location detail",
            "History retention",
            "Allowed hostnames",
            "Drop rules",
            "Effective collection settings",
            "Custom-data presence",
            "Tracking snippet"
          ]
        },
        {
          "entity": "project",
          "effect": "reads",
          "facts": [
            "Project ID",
            "Name",
            "Visibility",
            "Entities"
          ]
        },
        {
          "entity": "drop-rule",
          "effect": "reads",
          "facts": [
            "Scope",
            "Conditions"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "website::administration::entity-settings"
        }
      },
      "capability": "view-entity-settings"
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
    }
  ]
}
---

# Entity onboarding — configured source

## Trigger

Create a source and reach its settings and tracking snippet.

## Outcome

The new source exists and its settings/snippet have been read.
