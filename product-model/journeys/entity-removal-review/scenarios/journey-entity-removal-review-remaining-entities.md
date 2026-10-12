---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Website"
  },
  "steps": [
    {
      "text": "The Administrator confirms removal of the selected source configuration",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "web": {
          "place": "website::administration::entity-settings"
        }
      },
      "capability": "delete-entity"
    },
    {
      "text": "Deletion of the selected source configuration is confirmed.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "web": {
          "place": "website::administration::entity-settings"
        }
      },
      "capability": "delete-entity"
    },
    {
      "text": "Source configuration, associations and dependent key/membership group source-scope entries are removed. Stored event history remains; reusing the ID can reconnect retained history. The caller is carried to the remaining source list.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "entity",
          "effect": "removes"
        },
        {
          "entity": "project",
          "effect": "changes",
          "facts": [
            "Entities"
          ]
        },
        {
          "entity": "api-key",
          "effect": "changes",
          "facts": [
            "Entities"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "website::administration::entity-settings"
        }
      },
      "capability": "delete-entity"
    },
    {
      "text": "The Product carries the caller to the remaining-source list",
      "kind": "product",
      "actor": "administrator",
      "entities": [],
      "capability": "delete-entity",
      "contexts": {
        "web": {
          "place": "website::administration::entity-settings"
        }
      }
    },
    {
      "text": "The Administrator opens source discovery",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "web": {
          "place": "website::account::entity-list"
        }
      },
      "capability": "browse-entities"
    },
    {
      "text": "Source discovery is requested with a valid sign-in.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "web": {
          "place": "website::account::entity-list"
        }
      },
      "capability": "browse-entities"
    },
    {
      "text": "Visible source identities and names are returned with associated Project metadata filtered to enumerable Projects.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "entity",
          "effect": "reads",
          "facts": [
            "Entity ID",
            "Name",
            "Projects"
          ]
        },
        {
          "entity": "project",
          "effect": "reads",
          "facts": [
            "Project ID",
            "Name",
            "Visibility"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "website::account::entity-list"
        }
      },
      "capability": "browse-entities"
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

# Entity removal review — remaining entities

## Trigger

Remove source configuration and inspect remaining sources.

## Outcome

Configuration is removed, event history remains, and the destination list is read.
