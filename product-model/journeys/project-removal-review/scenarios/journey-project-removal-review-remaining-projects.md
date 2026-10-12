---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Website"
  },
  "steps": [
    {
      "text": "The Administrator confirms deletion of the selected grouping",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "web": {
          "place": "website::administration::project-settings"
        }
      },
      "capability": "delete-project"
    },
    {
      "text": "Deletion of the selected existing grouping is confirmed.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "web": {
          "place": "website::administration::project-settings"
        }
      },
      "capability": "delete-project"
    },
    {
      "text": "The Project, configuration and dependent access-scope references are removed; source configuration and event history remain. The caller is carried to the remaining Project list.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "project",
          "effect": "removes"
        },
        {
          "entity": "entity",
          "effect": "changes",
          "facts": [
            "Projects"
          ]
        },
        {
          "entity": "team",
          "effect": "changes",
          "facts": [
            "Projects"
          ]
        },
        {
          "entity": "api-key",
          "effect": "changes",
          "facts": [
            "Projects"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "website::administration::project-settings"
        }
      },
      "capability": "delete-project"
    },
    {
      "text": "The Product carries the caller to the remaining-grouping list",
      "kind": "product",
      "actor": "administrator",
      "entities": [],
      "capability": "delete-project",
      "contexts": {
        "web": {
          "place": "website::administration::project-settings"
        }
      }
    },
    {
      "text": "The Administrator opens discovery with the selected metric and range",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "web": {
          "place": "website::account::project-list"
        }
      },
      "capability": "browse-projects"
    },
    {
      "text": "grouping discovery is requested.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "web": {
          "place": "website::account::project-list"
        }
      },
      "capability": "browse-projects"
    },
    {
      "text": "The enumerable Project identities, visibility and associated-source metadata are returned. Unlisted direct access does not by itself place a Project in discovery.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "project",
          "effect": "reads",
          "facts": [
            "Project ID",
            "Name",
            "Visibility",
            "Entities"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "website::account::project-list"
        }
      },
      "capability": "browse-projects"
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
      "target": "crates/liwan/src/web/routes/dashboard.rs"
    }
  ]
}
---

# Project removal review — remaining projects

## Trigger

Remove a grouping and inspect remaining groupings.

## Outcome

The grouping is removed without deleting source history and destination discovery is read.
